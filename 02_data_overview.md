# Data Overview

This project uses historical bike-share data from Divvy (Chicago’s bike-share program), specifically for Q1 2019 and Q1 2020. The datasets were provided for use with RStudio due to their smaller size, to avoid memory overload on cloud platforms.

## Data Sources:
- Divvy_Trips_2019_Q1.csv
- Divvy_Trips_2020_Q1.csv

## Column Examples (Q1 2020):
- ride_id
- rideable_type
- started_at
- ended_at
- start_station_name
- end_station_name
- member_casual

## Column Examples (Q1 2019):
- trip_id
- bikeid
- start_time
- end_time
- from_station_name
- to_station_name
- usertype

## Notes:
- The two datasets have **different column names and structures**, so they must be cleaned and standardized before merging.
- 2019 data uses `usertype`, while 2020 uses `member_casual`.
- 2019 timestamps are `start_time`, `end_time`; 2020 uses `started_at`, `ended_at`.

## Data Handling Plan:
- Clean column names with `janitor::clean_names()`
- Standardize column formats (timestamps, membership type)
- Create new columns:
  - `ride_length` = ended_at - started_at
  - `day_of_week` = weekday(started_at)
- Combine both datasets into one dataframe
