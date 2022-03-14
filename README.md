# sql-is-declarative-answers
Quiz question:

Here is a SQL codeblock (for the BigQuery public data set):

```sql
SELECT
  SUM(number) AS num_people
FROM
  `bigquery-public-data.usa_names.usa_1910_current`;
```

To help you decide if SQL is procedural or declarative try the following tasks:

- Extend the query above to sum numbers of people for each name
- Only group and sum female names
- Sort the results with the most common names first
- Only show names that were used by over one million people
- Only get the top 5 most common American female names

Quiz answers

```sql
SELECT
  name,
  SUM(number) AS num_people
FROM
  `bigquery-public-data.usa_names.usa_1910_2013`
WHERE
  gender = 'F'
GROUP BY
  name
HAVING
  num_people > 1000000
ORDER BY
  num_people DESC
LIMIT
  5;
```
