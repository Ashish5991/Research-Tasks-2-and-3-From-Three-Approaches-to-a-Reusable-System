# Task 2/3: Identical Descriptive Statistics in Pure Python, Pandas, and Polars

Dataset file expected in the project folder:

```text
fb_ads_president_scored_anon.csv
```

Do **not** upload the dataset to GitHub. Keep only the scripts and documentation in the repo.

## Scripts

```bash
python pure_python_grouped_stats.py --file fb_ads_president_scored_anon.csv
python pandas_grouped_stats.py --file fb_ads_president_scored_anon.csv
python polars_grouped_stats.py --file fb_ads_president_scored_anon.csv
```

Each script produces a JSON output file:

```text
pure_python_results.json
pandas_results.json
polars_results.json
```

## Optional grouped analysis

By default, each script automatically selects up to 3 categorical/date-like columns with reasonable cardinality and computes grouped summaries.

For stronger control, pass the same grouping columns into all three scripts:

```bash
python pure_python_grouped_stats.py --file fb_ads_president_scored_anon.csv --group-cols "COLUMN_1,COLUMN_2"
python pandas_grouped_stats.py --file fb_ads_president_scored_anon.csv --group-cols "COLUMN_1,COLUMN_2"
python polars_grouped_stats.py --file fb_ads_president_scored_anon.csv --group-cols "COLUMN_1,COLUMN_2"
```

Replace `COLUMN_1,COLUMN_2` with real columns from your dataset, such as sponsor, page, candidate, region, date, or organization columns.

## Statistics computed

At the dataset level:

- total rows
- total columns
- column names
- missing count and missing percentage by column
- inferred type by column

For numeric columns:

- count
- mean
- minimum
- maximum
- sample standard deviation
- median

For categorical/date-like columns:

- count
- number of unique values
- mode
- mode frequency
- top 5 most frequent values

At grouped levels:

- row count per group
- same numeric statistics within each group
- categorical frequency summaries within each group

## Dependencies

```bash
pip install -r requirements.txt
```
