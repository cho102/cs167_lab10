# Lab 10

## Student information

* Full name: Cindy Ho
* E-mail: cho102@ucr.edu
* UCR NetID: cho102
* Student ID: 862151318

## Answers

* (Q1) What is the result?

  ```text
  # Replace here with the result
  [
        3
  ]
  ```

* (Q2) Which query did you use and what is the answer?
  
  ```sql
  SELECT DISTINCT(primary_type)
  From ChicagoCrimes
  WHERE location_description="GAS STATION";
  ```

  ```text
  [
        {
                "primary_type": "DECEPTIVE PRACTICE"
        },
        {
                "primary_type": "ROBBERY"
        },
        {
                "primary_type": "THEFT"
        },
        {
                "primary_type": "BATTERY"
        },
        {
                "primary_type": "MOTOR VEHICLE THEFT"
        }
  ]  
  ```

* (Q3) Include the query in your README file

  ```sql
  SELECT year, count(*) AS count FROM (
    SELECT get_year(parse_datetime(date_value, "MM/DD/YYY hh:mm:ss a")) AS year
    FROM ChicagoCrimes
    ) AS years
  GROUP BY year
  ORDER BY count desc;
  ```

* (Q4) Which `district` has the most number of crimes? Include the query and the answer in the README file.

  ```sql
  SELECT district, count(*) AS count FROM ChicagoCrimes
  GROUP BY district
  ORDER BY count desc;
  ```

  ```text
  [
        {
                "district": 18,
                "count": 108587
        },
        {
                "district": 1,
                "count": 16482
        },
        {
                "district": 12,
                "count": 1
        }
  ]
  ```

* (Q5) Include the query in your submission.

  ```sql
  SELECT count(8)
  FROM(
    SELECT year_month, count(*) AS count FROM (
    SELECT print_datetime(parse_datetime(date_value, "MM/DD/YYY hh:mm:ss a"), "YYYY/MM") AS year_month
    FROM ChicagoCrimes) AS ymonths
    GROUP BY year_month
    ORDER BY year_month
  ) AS total;
  ```

* (Q6) What is the total number of results produced by this query (not only the shown ones)?
