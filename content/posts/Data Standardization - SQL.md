---
title: "Data Cleaning : Data Standardization with SQL"
date: 2023-06-08T06:00:23+06:00
hero: /images/posts/writing-posts/analytics.svg
description: Data standardization is a fundamental step in data management to ensure data quality and consistency making it suitable for analysis, reporting, and decision-making.Overall, failing to standardize data can result in data that is difficult to work with, error-prone, and less reliable.
theme: Toha
menu:
  sidebar:
    name: Data Cleaning - Data Standardization with SQL
    identifier: data-cleaning
    weight: 500
---

Data standardization is a fundamental step in data management to ensure data quality and consistency making it suitable for analysis, reporting, and decision-making.Overall, failing to standardize data can result in data that is difficult to work with, error-prone, and less reliable.

Let’s explore the process of data cleaning and put it into practice using a specific dataset. The dataset follows the schema outlined below…

```sql

--Below script works on mysql

CREATE database pizza_runner;

USE pizza_runner;

CREATE TABLE runner_orders (
    order_id INTEGER,
    runner_id INTEGER,
    pickup_time VARCHAR(19),
    distance VARCHAR(7),
    duration VARCHAR(10),
    cancellation VARCHAR(23)
);
    
INSERT INTO runner_orders
  (order_id, runner_id, pickup_time, distance, duration, cancellation)
VALUES
  ('1', '1', '2020-01-01 18:15:34', '20km', '32 minutes', ''),
  ('2', '1', '2020-01-01 19:10:54', '20km', '27 minutes', ''),
  ('3', '1', '2020-01-03 00:12:37', '13.4km', '20 mins', NULL),
  ('4', '2', '2020-01-04 13:53:03', '23.4', '40', NULL),
  ('5', '3', '2020-01-08 21:10:57', '10', '15', NULL),
  ('6', '3', 'null', 'null', 'null', 'Restaurant Cancellation'),
  ('7', '2', '2020-01-08 21:30:45', '25km', '25mins', 'null'),
  ('8', '2', '2020-01-10 00:15:02', '23.4 km', '15 minute', 'null'),
  ('9', '2', 'null', 'null', 'null', 'Customer Cancellation'),
  ('10', '1', '2020-01-11 18:50:20', '10km', '10minutes', 'null');



SELECT 
    *
FROM
    runner_orders;

```
More information about the above database can be found on this link.

### Problem Statement:

Calculating the average from the original ‘duration’ column yields an incorrect value of 18.4.

