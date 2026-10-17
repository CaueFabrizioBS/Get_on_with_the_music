# Get on with the Music

A comparison of music listening activity in two cities, **Springfield** and **Shelbyville**, using data from an online music streaming service. The project walks through a typical analyst workflow: data overview, preprocessing and hypothesis testing.

## Question

Does user activity differ depending on the day of the week and on the city?

## Main findings

* **The hypothesis holds.** Activity changes during the week and the pattern is different in each city.
* **Springfield is much more active:** 42,741 tracks played against 18,512 in Shelbyville. On some days the gap is above 10 thousand plays.
* **Springfield** peaks on Friday (15,945 plays) and has its lowest point on Wednesday (11,056).
* **Shelbyville** peaks on Wednesday (7,003 plays) and has its lowest point on Monday (5,614).

## What the notebook does

1. **Data overview:** inspects the 65,079 rows and seven columns, and identifies header, missing value and duplicate problems.
2. **Preprocessing:**
    * Standardizes the column names (lowercase, no spaces, snake_case).
    * Fills the missing values in `track`, `artist` and `genre` with `'unknown'`.
    * Removes 3,826 fully duplicated rows (61,253 rows remain).
    * Fixes implicit duplicates in `genre` (`hip`, `hop` and `hip-hop` become `hiphop`, and `türkçe` becomes `türk`), reducing the unique genres from 269 to 265.
3. **Hypothesis testing:** groups the plays by city, by day (Monday, Wednesday and Friday) and by both, using `groupby` and a custom function.

## Repository structure

```
Get_on_with_the_music/
├── music_by_city.ipynb
├── music_project_en.csv
├── README.md
└── requirements.txt
```

## Run locally

```
git clone https://github.com/<your-username>/Get_on_with_the_music.git
cd Get_on_with_the_music
python -m venv .venv
.venv\Scripts\activate          # Windows
source .venv/bin/activate       # macOS / Linux
pip install -r requirements.txt
pip install ipykernel           # to run the notebook in VS Code or Jupyter
```

Then open `music_by_city.ipynb` and run all cells. The notebook reads the CSV from the project root, so it must be opened from there.

## Tech stack

Python, pandas, Jupyter Notebook.
