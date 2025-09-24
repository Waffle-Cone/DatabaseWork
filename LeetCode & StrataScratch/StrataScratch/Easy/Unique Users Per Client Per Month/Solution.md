# Unique Users Per Client Per Month

**StrataScratch ID:** 2024  
**Difficulty:** Easy  
**Last Updated:** September 2025

## Question

Write a query that returns the number of unique users per client for each month. Assume all events occur within the same year, so only month needs to be in the output as a number from 1 to 12.

**Table:** fact_events

- client_id (text)
- customer_id (text)
- event_id (bigint)
- event_type (text)
- id (bigint)
- time_id (date)
- user_id (text)

---

## My Solution (MySQL)

```sql
SELECT
    CLIENT_ID,
    MONTH(TIME_ID) AS month,
    COUNT(DISTINCT USER_ID) AS users_num
FROM fact_events
GROUP BY CLIENT_ID, month


```
