# Investment Calculator Lab

**NOTE: On the next revision of this lab, it might be worth limiting the data that is shown during each challenge. Instead of one whole data table, there would be several smaller tables showing *only* relevant data.**

Many financial advisors suggest that young people begin saving money early in life for their retirements. Saving comes in form of paying off debts; investing in stocks, bonds, and mutual funds; and putting money away in retirement accounts like IRAs and Roth IRAs. Often, investment advisors will provide clients with calculators to see how investments would have paid off if they had put money away. Although past performance doesn't imply future returns, we're going to look at several funds to see how much money a client could have made if they had invested at different times in the past. 

In general, it's possible to write a set of instructions (an algorithm) that takes in historical prices and calculates what the value of a past investment would be today. In this lab, you'll be writing python methods to calculate the current value of past investments.

Take a look at this chart that provides some historical data for a few financial funds in units of Cost Per Share (CPS):

| Fund | 1980 CPS (USD) | 1996 CPS (USD) | 2012 CPS (USD) | 2016 CPS (USD) | Current CPS (USD) |
| :---: | :---: | :---: | :---: | :---: | :---: |
| Fund A | $2.50 | $3.75 | $4.10 | $5.10 | $5.95 |
| Fund B | $12.02 | $14.10 | $15.76 | $18.08 | $21.01 |
| Fund C | $8.65 | $8.03 | $11.15 | $19.82 | $23.01 |
| Fund D | $0.63 | $1.22 | $1.45 | $2.01 | $1.83 |

## Instructions

1) Create a function called `number_shares_a()` that only accepts an `investment` amount and returns the number of shares of Fund A which that investment could buy today.

```python
def number_shares_a(investment):
	# your code here
```

**Example:** When I run `number_shares_a(300)` for a $300 investment, it should return **50.42** because $300 could buy 50.42 shares of Fund A.

```python
print(number_shares_a(300))
# 50.42
```

2) Create a more-general function called `number_shares()` that takes in an `investment` amount and a `fund`. It should return the number of shares of that fund which that investment could buy today.

```python
def number_shares(investment, fund):
	# your code here
```

**Example:** `number_shares(1000, "c")` should return **43.46** because a $1,000 investment could purchase 43.46 shares of Fund C.

```python
print(number_shares(1000, "c"))
# 43.46
```

3) Create a more flexible calculator method called `history_shares()` that takes in an `investment` amount, `fund`, and `year` and returns the number of shares that money could buy in that year.

```python
def history_shares(investment, fund, year):
	# your code here
```

**Example:** To find out how many shares of Fund B $5,000 could buy in 1996, `history_shares(5000, "b", 1996)` should return **354.61** because $5,000 could buy 354.61 shares at the 1996 price of $14.10.

```python
print(history_shares(5000, "b", 1996))
# 354.61
```

*Bonus:* if no year is given, have `history_shares` default to the current value.

**Advanced Bonus Challenge:**

4) What is the change of an investment over time? Create a method `calculate_profit()` that accepts an initial `investment` amount, the `fund`, and the initial investment `year`, and returns the current *profit* made on the initial investment. This is an open ended one - there are many ways to do this!

```python
def calculate_profit(investment, fund, year):
	# your code here
```

> Hint: you might be able to use your `history_shares()` function to make this easier.

**Example:** To calculate the profit of a $2,000 investment in Fund D in 1996, `calculate_profit(2000, "d", 1996)` should return **1000**.

```python
print(calculate_profit(2000, "d", 1996))
# 1000
```

*Bonus:* Format the output of the function as USD currency, so instead of `1000`, the function should output **$1000.00**.

```python
print(calculate_profit(2000, "d", 1996))
# $1000.00
```

**Double Advanced Bonus Challenge:**

5) Which investment is the best? Create a method `best_choice()` that accepts an `investment` amount and a `year`, and returns the name of the fund that would have made the most money for the investor. 

```python
def best_choice(investment, year):
	# your code here
```

**Example:** To figure out which fund an investor making a $1,000 investment in 2012 would have made the most money from, `best_choice(1000, 2012)` would return **Fund C**.

```python
print(best_choice(1000, 2012))
# Fund C
```

*Bonus:* In addition to the name of the fund, also return how much money the investor would have *earned*.

```python
print(best_choice(1000, 2012))
# Fund C 1063.68
```

**Triple Advanced Bonus Challenge:**

6) Consider the current profit difference between making an investment in a fund several years apart. Create a method `investment_diff()` that accepts an `investment` amount, a `fund`, and two `year` values and returns the current profit difference if the money had been made earlier vs. later.

```python
def investment_diff(investment, fund, year1, year2):
	# your code here
```

**Example:** To figure out how much more money an investor would have made investing $500 in Fund A in 1980 vs. 2012, `investment_diff(500, "a", 1980, 2012)` would return **464.39**.

```python
print(investment_diff(500, "a", 1980, 2012))
# 464.39
```

*Bonus:* How can you account for a sloppy investment advisor who puts the years in a different order than you expect?

```python
print(investment_diff(500, "a", 1980, 2012)) # vs.
print(investment_diff(500, "a", 2012, 1980))
```
