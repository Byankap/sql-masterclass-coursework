<p align="center">
    <img src="./../images/sql-masterclas-banner.png" alt="sql-masterclass-banner">
</p>

[![forthebadge](./../images/badges/version-1.0.svg)]()
[![forthebadge](https://forthebadge.com/images/badges/powered-by-coffee.svg)]()
[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)]()
[![forthebadge](https://forthebadge.com/images/badges/ctrl-c-ctrl-v.svg)]()

# Step 5 - Let the Data Analysis Begin!

[![forthebadge](./../images/badges/go-to-previous-tutorial.svg)](https://github.com/datawithdanny/sql-masterclass/tree/main/course-content/step4.md)
[![forthebadge](./../images/badges/go-to-next-tutorial.svg)](https://github.com/datawithdanny/sql-masterclass/tree/main/course-content/step6.md)

Now that we've explored all 3 of our tables - let's try to first visualize how each of the tables are joined onto eachother using an Entity Relationship Diagram or ERD for short!

## What is an ERD?

ERDs are very useful to visualize the relationships between columns in tables - especially when it comes to combining them together using tables joins (something we'll cover in this current tutorial)

Below you will see the ERD for our current case study - the most important thing is to notice how all of the columns relate to one another.

![Crypto Case Study ERD](assets/crypto-erd.png)

# Realistic Analytics

Even though we have been exploring our datasets and exploring a few of the basic SQL concepts required for data analysis - we have yet to combine our SQL queries into a single focused analytical process to solve a larger problem. This is our opportunity to try this now!

Let's say that we wish to analyse our overall portfolio performance and also each member's performance based off all the data we have in our 3 tables.

## Analyse the Ranges

Firstly - let's see what is the range of data we have to play with!

### Question 1

> What is the earliest and latest date of transactions for all members?

> My Solution: 

```

```
<br>

| earliest_date | latest_date |
| ------------- | ----------- |
| 2017-01-01    | 2021-08-27  |

### Question 2

> What is the range of `market_date` values available in the prices data? 

> My Solution: 

```

```
<br>

| earliest_date | latest_date |
| ------------- | ----------- |
| 2017-01-01    | 2021-08-29  |
<br>

## Joining our Datasets

Now that we now our date ranges are from January 2017 through to almost the end of August 2021 for both our prices and transactions datasets - we can now get started on joining these two tables together!

Let's make use of our ERD shown above to combine the `trading.transactions` table and the `trading.members` table to answer a few simple questions about our mentors!

### Question 3

> Which top 3 mentors have the most Bitcoin quantity as of the 29th of August? 

> My Solution: 

```

```
<br>

| first_name |     total_quantity      |
| ---------- | ----------------------- |
| Nandita    | 4160.219869506641749735 |
| Leah       |  4046.09089667256706404 |
| Ayush      |  3945.19808326050497234 |
<br>

## Calculating Portfolio Value

Now let's combine all 3 tables together using only strictly `INNER JOIN` so we can utilise all of our datasets together.

### Question 4

> What is total value of all Ethereum portfolios for each region at the end date of our analysis? Order the output by descending portfolio value 

> My Solution: 

```

```
<br>

|    region     |        ethereum_value        |    avg_ethereum_value     |
| ------------- | ---------------------------- | ------------------------- |
| Australia     | 40076021.0922707343527642712 | 10752.8900167080049298064 |
| United States | 50688412.2772532532882719016 | 10549.0972481276281626456 |
| Asia          |  5011670.9776990206825808176 |  8933.4598532959370421432 |
| India         |   6276426.482786365114210656 |   8036.397545181005116104 |
| Africa        |  2183933.3382704268238606128 |  3899.8809611971907658600 |
<br>

### Question 5

> What is the average value of each Ethereum portfolio in each region? Sort this output in descending order

> My Solution: 

```

```

<br>

|    region     |    avg_ethereum_value     |
| ------------- | ------------------------- |
| Australia     | 10752.8900167080049298064 |
| United States | 10549.0972481276281626456 |
| Asia          |  8933.4598532959370421432 |
| India         |   8036.397545181005116104 |
| Africa        |  3899.8809611971907658600 |
<br>

Mmm hang on a second...does the output for the above query look correct to you?

Let's try again - this time we will calculate the total sum of portfolio value and then manually divide it by the total number of mentors in each region! 

> My Solution: 

```

```

<br>

|    region     |        ethereum_value        | mentor_count |      avg_ethereum_value      |
| ------------- | ---------------------------- | ------------ | ---------------------------- |
| Australia     | 40076021.0922707343527642712 |            4 | 10019005.2730676835881910678 |
| United States | 50688412.2772532532882719016 |            7 |  7241201.7538933218983245574 |
| India         |   6276426.482786365114210656 |            1 |   6276426.482786365114210656 |
| Asia          |  5011670.9776990206825808176 |            1 |  5011670.9776990206825808176 |
| Africa        |  2183933.3382704268238606128 |            1 |  2183933.3382704268238606128 |
<br>

[![forthebadge](./../images/badges/go-to-previous-tutorial.svg)](https://github.com/datawithdanny/sql-masterclass/tree/main/course-content/step4.md)
[![forthebadge](./../images/badges/go-to-next-tutorial.svg)](https://github.com/datawithdanny/sql-masterclass/tree/main/course-content/step6.md)