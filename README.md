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
  /* Replace here with your query */
  ```

  ```text
  # Replace here with your answer
  ```

* (Q5) Include the query in your submission.

  ```sql
  /* Replace here with your query */
  ```

* (Q6) What is the total number of results produced by this query (not only the shown ones)?
