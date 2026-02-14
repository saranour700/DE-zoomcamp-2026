# Module 2 Homework Solutions

## Quiz Questions

### Q1. Within the execution for Yellow Taxi data for the year 2020 and month 12: what is the uncompressed file size?
- **Answer:** `134.5 MiB`
- **Steps:** Ran the flow for Yellow/2020/12 and checked the `size` in the Outputs tab.

### Q2. What is the rendered value of the variable file when the inputs taxi is set to green, year is set to 2020, and month is set to 04?
- **Answer:** `green_tripdata_2020-04.csv`
- **Explanation:** Based on the variable template:  
  `{{inputs.taxi}}_tripdata_{{inputs.year}}-{{inputs.month}}.csv`

### Q3. How many rows are there for the Yellow Taxi data for all CSV files in the year 2020?
- **Answer:** `24,648,499`
- **SQL Query:**
```sql
SELECT count(*) 
FROM yellow_tripdata 
WHERE filename LIKE 'yellow_tripdata_2020%';
```

### Q4. How many rows are there for the Green Taxi data for all CSV files in the year 2020?
- **Answer:** `1,734,051`
- **SQL Query:**
```sql
SELECT count(*) 
FROM green_tripdata 
WHERE filename LIKE 'green_tripdata_2020%';
```

### Q5. How many rows are there for the Yellow Taxi data for the March 2021 CSV file?
- **Answer:** `1,925,152`
- **SQL Query:**
```sql
SELECT count(*) 
FROM yellow_tripdata 
WHERE filename = 'yellow_tripdata_2021-03.csv';
```

### Q6. How would you configure the timezone to New York in a Schedule trigger?
- **Answer:** Add a `timezone` property set to `America/New_York` in the Schedule trigger configuration.
- **Explanation:** Kestra uses the IANA Time Zone database format (e.g., `America/New_York`) to correctly handle scheduling and daylight saving time.

