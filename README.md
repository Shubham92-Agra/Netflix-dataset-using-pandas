# Netflix-dataset-using-pandas
Netflix data

import pandas as pd

# =====================================
# DATASET 2 : NETFLIX DATASET
# =====================================

netflix_data = [
    {"show_id": "s1", "type": "Movie", "title": "Dick Johnson Is Dead", "director": "Kirsten Johnson", "country": "United States", "release_year": 2020, "duration": "90 min", "genre": "Documentaries"},
    {"show_id": "s2", "type": "TV Show", "title": "Blood & Water", "director": "Nosipho Dumisa", "country": "South Africa", "release_year": 2021, "duration": "2 Seasons", "genre": "Drama"},
    {"show_id": "s3", "type": "Movie", "title": "The Last Kids on Earth", "director": None, "country": "United States", "release_year": 2019, "duration": "95 min", "genre": "Animation"},
    {"show_id": "s4", "type": "TV Show", "title": "Money Heist", "director": "Álex Pina", "country": "Spain", "release_year": 2018, "duration": "5 Seasons", "genre": "Crime"},
    {"show_id": "s5", "type": "Movie", "title": "The Social Dilemma", "director": "Jeff Orlowski", "country": "United States", "release_year": 2020, "duration": "94 min", "genre": "Documentaries"},
    {"show_id": "s6", "type": "Movie", "title": "Extraction", "director": "Sam Hargrave", "country": "United States", "release_year": 2020, "duration": "117 min", "genre": "Action"},
    {"show_id": "s7", "type": "TV Show", "title": "Dark", "director": "Baran bo Odar", "country": "Germany", "release_year": 2017, "duration": "3 Seasons", "genre": "Sci-Fi"},
    {"show_id": "s8", "type": "Movie", "title": "3 Idiots", "director": "Rajkumar Hirani", "country": "India", "release_year": 2009, "duration": "170 min", "genre": "Comedy"},
    {"show_id": "s9", "type": "TV Show", "title": "Sacred Games", "director": "Anurag Kashyap", "country": "India", "release_year": 2018, "duration": "2 Seasons", "genre": "Crime"},
    {"show_id": "s10", "type": "Movie", "title": "Inception", "director": "Christopher Nolan", "country": "United States", "release_year": 2010, "duration": "148 min", "genre": "Sci-Fi"}
]

netflix_df = pd.DataFrame(netflix_data)

print("\n\nNETFLIX DATASET")
print(netflix_df.head())
print("\n")
print(netflix_df.info())
print("\nMissing Values:")
print(netflix_df.isnull().sum())

# Fill missing director
netflix_df["director"] = netflix_df["director"].fillna("Unknown")

# Extract numeric duration
netflix_df["duration_num"] = netflix_df["duration"].str.extract(r"(\d+)").astype(int)

print("\nCleaned Netflix Dataset")
print(netflix_df)
