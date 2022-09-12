---
author: Wenjia Zhu
categories:
- Finance
- Life
date: "2022-09-07"
draft: false
excerpt: This blog documents my recent learning with the ["Foundational Finance for Strategic Decision Making Specialization"](https://www.coursera.org/specializations/foundational-finance) provided by the University of Michigan on Coursera. The specialization consists of four courses introducing the concept of Time Value of Money (TVM) and some basic understanding of stocks and bonds. The blog serves as a documentary of all the notes I summarized from my learning.
layout: single-sidebar
subtitle: 
tags:
- TVM
- Stocks
- Bonds
title: What is Time Value of Money (TVM) and its world applications 
---

In the past several weeks, I have been studying with this ["Foundational Finance for Strategic Decision Making Specialization"](https://www.coursera.org/specializations/foundational-finance) offered by the University of Michigan on Coursera. The objectives of this specialization is to help learners with interests in the application of modern finance make good and thoughtful personal decisions. It consists of four courses, all build on each other, starting with the introduction of Time Value of Money (TVM) segue into the two most common types of investment, stocks and bonds. 

---

## 1. Time Value of Money 💰

The Time Value of Money (TVM) is the foundational principle of finance, a sum of money in the hand has greater value than the same sum to be paid in the future [^definition]. It is also referred to as present discounted value. The most fundamental TVM formula accounts in the following variables:
+ FV = future value of money
+ PV = present value of money
+ r = interest rate
+ m = number of compounding periods


$$
FV = PV * (1 + r)^m
$$

---
The courses provide some real-world examples in assignments to help learners better understand the concepts. I attach some good examples as follows:

**Q1. Carlos goes to the bank to take out a personal loan. The stated annual interest rate is 8%, but interest is compounded quarterly and he will make monthly payments. What is the EAR?** 

Answer: 8.24%
<details>
  <summary>Click for Solution</summary>
    $$
    EAR = (1 + \frac{8\%}{4})^4 - 1
    $$
</details>

<br>

**Q2. Abebi, who has just celebrated her 31st birthday, will retire on her 60th birthday, and she has just set up a retirement plan to pay her income starting on her retirement day, and to continue paying for 19 more years. Abebi's goal is to receive $110,000 for each of these twenty years. In creating her retirement account, Abebi has committed to set aside equal investments at the end of each year, for the next 28 years starting on her 32nd birthday. If the annual interest rate is 7%, how big should Abebi's equal investments be?** (Enter just the number in dollars without the $ sign or a comma and round off decimals to the closest integer, i.e., rounding $30.49 down to $30 and rounding $30.50 up to $31.)

Answer: 14441
<details>
  <summary>Click for Solution</summary>
  
    PMT = $110,000 
    m = 20 
    r = 7% 
    The present value at age 60 = PV(0.07, 20, 110000) = $1,165,341.57, 
    also considered as future value at age 31
    PMT(0.07, 28, ,1165341.57) = $14,440.83
</details>

<br>

**Q3. Two years ago Abilia purchased a $13,000 car; she paid $2,500 down and borrowed the rest. She took a fixed rate 60-month installment loan at a stated rate of 7.0% per year. Interest rates have fallen during the last two years and she can refinance her car by borrowing the amount she still owes on the car at a new fixed rate of 4% per year for 3 years. Should Abilia refinance her loan? How much will she save per month for the remainder of the loan life if she decides to refinance?**

Answer: Yes, save $9.11
<details>
  <summary>Click for Solution</summary>
  
    PV = $13,000 - $2,500 = $10,500
    monthly payment = PMT(0.07/12, 60, 10500) = $207.91
    At the year 3, the present value of remaining loan = 
    PV(0.07/12, 36, 207.91) = $6,733.55
    monthly payment after refinance = PMT(0.04/12, 36, 6733.55) = $198.80
    Difference = $207.91 - $198.80 = $9.11
</details>

<br>

**Q4. You have been living in the house you bought 6 years ago for $400,000. At that time, you took out a loan for 80% of the house at a fixed rate 20-year loan at an annual stated rate of 8.5%. You have just paid off the 72th monthly payment. Interest rates have meanwhile dropped steadily to 4.5% per year, and you think it is finally time to refinance the remaining balance over the residual loan life. But there is a catch. The fee to refinance your loan is $4,500. Should you refinance the remaining balance? How much would you save/lose if you decided to refinance?**

Answer: Yes, gain $68,890.61
<details>
  <summary>Click for Solution</summary>
  
    monthly payment = PMT(0.085/12, 20*12, 400000*80%) = $2,777.03
    present value of remaining loan = PV(0.085/12, 20*12-72, 2777.03) = $272,280.02
    monthly payment after refinance = PMT(0.045/12, 20*12-72, 272280.02) = $2,187.43
    Difference (savings per month) = $2,777.03 - $2,187.43 = $589.60
    present value of savings = PV(0.045/12, 20*12-72, -589.60) - 4500 = $68,890.61
</details>

<br>

**Q5. You are interested in a new Ford Taurus. After visiting your Ford dealer, doing your research on the best leases available, you have three options.**

**(i) Purchase the car for cash and receive a $1,800 cash rebate from Dealer A. The price of the car is $18,000.**

**(ii) Lease the car from Dealer B. Under this option, you pay the dealer $500 now and $225 a month for each of the next 36 months (the first $225 payment occurs 1 month from today). After 36 months you may buy the car for $10,100.**

**(iii) Purchase the car from Dealer C who will lend you the entire purchase price of the car for a zero interest 36-month loan with monthly payments. The car price is $18,000. Suppose the market interest rate is 6%. What is the net cost today of the cheapest option?**

(Enter just the number in dollars without the $ sign or a comma and round off decimals to the closest integer, i.e., rounding $30.49 down to $30 and rounding $30.50 up to $31.)

Answer: 16200
<details>
  <summary>Click for Solution</summary>
  
    Net Cost from:
    (i)   Dealer A: $18,000 - $1,800 = $16,200
    (ii)  Dealer B: 500 + PV(0.06/12, 36, -225) + PV(0.06, 3,, -10100) = $16,376.13
    (iii) Dealer C: $18,000
</details>

<br>

---
## 2. Bonds 💵

Bonds are technically a form of "IOU" (I Owe You), a loan from you to a company or government under a contract of promising to repay the money with interest by a certain date. There are two general types of bonds, pure discount (or zero-coupon) bonds and coupon bonds. 

+ **Zero coupon bonds** are bonds that do not pay interest during the life of the bonds, and the investors receive the face value of the bonds when they mature.
+ **Coupon bonds** are type of bonds that include attached coupons and pay periodic interest payments (typically semi-annual payments) during their lifetime and their par values at maturity. 

Yield to maturity (YTM) is the total return anticipated on a bond if is held until it matures[^ytm].

**Q6. What is the yield to maturity (YTM) of a zero coupon bond with a face value of $1,000, current price of $800 and maturity of 7 years? Recall that the compounding interval is 6 months and the YTM, like all interest rates, is reported on an annualized basis.** (Allow two decimals in the percentage but do not enter the % sign.)

Answer: 3.21
<details>
  <summary>Click for Solution</summary>
  
    YTM = RATE(7*2,, -800, 1000) * 2 = 3.21%
</details>

<br>

The price of a bond is determined by the present value formula:
+ for zero-coupon bonds: 
$$
Bond\ Price = \frac{Face\ Value}{(1 + YTM) ^ n}
$$
$$
n = number\ of\ years\ until\ maturity
$$
+ for coupon bonds:
$$
Bond\ Price = \frac{C}{1 + YTM} + \frac{C}{(1 + YTM)^2} + ... + \frac{C}{(1 + YTM)^n} + \frac{Face\ Value}{(1 + YTM) ^ n}
$$
$$
C = coupon\ payment
$$

**Q7. Suppose Wolverine Steel Company wishes to issue a $100,000 bond with a maturity of 4 years to raise $78,101. The market requires a yield to maturity (YTM) of 11.0% for this company's borrowing/debt. How much coupon will the company have to pay every six months?** (Enter just the number in dollars without the $ sign or a comma and round off decimals to the closest integer, i.e., rounding $30.49 down to $30 and rounding $30.50 up to $31.)

Answer: 2043
<details>
  <summary>Click for Solution</summary>
  
    Coupon = PMT(0.11/2, 4*2, 78101, -100000) = $2,042.94
</details>

<br>

### Risks of Bonds
The uncertainty concerning bond values/prices due to interest rates fluctuation is known as the **interest rate risk** of bonds. There are two types of interest rate risks: **price risk** and **coupon reinvestment risk**, which are the main risks tied to government bonds. For a zero-coupon bond, the bond price in any period before the maturity date is unknown and determined by the interest rate. For a coupon bond, the value of the coupons received periodically are also affected by the interest rate. If the interest rate at a given period goes down, the price of the bond at that period goes up but the values carried forward from the received coupons declines. Corporate bonds almost always pay coupons. Like government bonds, they are subject to interest rate risks, but they are also subject to **default risk**. The default risk is the chance of not getting paid. Rating agencies such as Moody's, S&P, etc rate corporate bonds in the U.S. Most "bonds" are contracts/loans issued by a bank.



---
## 3. Stocks 📈

Stocks represent partial ownership, or equity, in a company, translating into "shares". Unlike coupons with a determined maturity date, stocks can be endless as long as the company keeps in business. How to determine the present value of the stock? We'll use a stock with dividends as an example, and imagine owning it for only one period. Consider the stock's price is P1 and it provides dividend DIV1 at year 1, the present value of stock is:
$$
P_0 = \frac{DIV_1 + P_1}{1 + r}
$$
$$
r = interest\ rate
$$

Then how can we calculate the stock's price at year 1, P1? This should be straightforward, as it is determined by the dividend and stock's price in year 2. Same thing repeats for the stock's price in the following years, because the stock has no fixed maturity date theoretically. And therefore we can transform the above formula into:
$$
P_0 = \frac{DIV_1 + P_1}{1 + r} = \frac{DIV_1 + \frac{DIV_1 + P_2}{1 + r}}{1 + r} = \frac{DIV_1}{1 + r} + \frac{DIV_2}{(1 + r)^2} + ... + \frac{DIV_n}{(1 + r)^n} + \frac{P_n}{(1 + r)^n} 
$$

Since we won't be able to know the dividend and price for the next period, these values are all expected values. When it approaches to the end, the stock's price in year n, Pn, is negligible. We can further simplify the problem by assuming the dividends remain the same every year, and the formula is equal to calculating the present value of a perpetuity:
$$
PV_\infty = \frac{C}{r}
$$
$$
where: C = Cash\ flow = Dividend
$$

The formula to calculate present value of a perpetuity, with growth at rate g is:
$$
PV_\infty(g) = \frac{C}{r - g}
$$

**Q8. The stock of Alydar Oil, an all-equity firm, is currently trading at $30 per share, after just having paid a $2.40 per share dividend. The market expects a dividend of $3.10 per share to be paid one year from today. If the equity cost of capital (same as discount rate for equity) is 12% for this firm, the expected ex-dividend price (the stock price after the dividend is paid next year) in one year (t = 1) should be closest to**

Answer: $30.50
<details>
  <summary>Click for Solution</summary>
  
    Ex-dividend price = FV(0.12, 1,, -30) - 3.1 = $30.5
</details>

<br>

### Good or Bad Growth
Suppose you know this about Macrosoft, Inc.
+ It is expected to earn 10% on its existing assets
+ Has $60 of capital per share
+ The market capitalization rate is 12%
+ The company is not planning to grow...
What should Macrosoft, Inc.'s shares trade at?

We know `ROI = 10%`, `r = 12%` and `g = 0`

$$
P_0 = \frac{DIV}{r} = \frac{EPS}{r} = \frac{60 * 0.10}{0.12} = 50
$$

***New Growth Policy: Scenario I***

Suppose Macrosoft, Inc. announces an exciting growth policy that plows back 70% of its earnings every year at the same ROI as its existing assets.
+ What growth rate will this policy generate?
+ What will happen to Macrosoft, Inc.'s share price?

The intent of plow-back is to reinvestment. The growth rate requires two elements, `b` the reinvestment rate and `ROI` return on the reinvestment. And thus `growth rate = b * ROI = 0.70 * 0.10 = 0.07`.
$$
P_0 = \frac{DIV}{r - g} = \frac{EPS}{r - g} = \frac{60 * 0.10 * (1 - 0.7)}{0.12 - 0.07} = 36
$$

***New Growth Policy: Scenario II***

Suppose Macrosoft, Inc. announces an alternative growth policy that plows back 50% of its earnings every year at an ROI of 14%.

The growth rate `g = b * ROI = 0.50 * 0.14 = 0.07`, exactly the same as the Scenario I. However, since `IRR > r`，
$$
P_0 = \frac{DIV}{r - g} = \frac{60 * 0.10 * (1 - 0.5)}{0.12 - 0.07} = 60
$$

The growth rate is built in cash flow, so it could be wrong to emphasize on growth. In the real world, the company lives in long run, but the management team is short-lived, and therefore they tend to chase after growth focused on cash flows. However, it is important to understand that the value created is embedded in the company's assets rather than cash flows.

In summary, here are some important formulas related to stocks:
+ the core equation of earning per share (EPS) is `CPS * ROI = EPS = DIV/EPS (known as 1 - b) + RE/EPS (known as b)`.
+ `g = b * ROI`
+ the stock price is `$$P_0 = \frac{DIV_1}{r - g}$$`

**Q9. You are deciding whether to add Bard Publishing to your portfolio, but you are concerned about your projection for their growth rate. Bard's cost of equity capital (the discount rate for equity) is known to be 8% and they just paid a dividend of $3.50 per share. When calculating the value of the stock today, you cannot decide if the constant growth rate will be 4.5% or 5.5%. By how much does this seemingly small difference impact your valuation, i.e., the price per share?** (Enter just the number in dollars without the $ sign or a comma and round off decimals to the closest integer, i.e., rounding $30.49 down to $30 and rounding $30.50 up to $31.)

Answer: $43
<details>
  <summary>Click for Solution</summary>
    
    (a) option with 4.5%:
    the price per share P0 = 3.5 * 1.045 / (0.08 - 0.045) = $104.5
    (b) option with 5.5%
    the price per share P0 = 3.5 * 1.045 / (0.08 - 0.045) = $147.7
</details>

<br>

**Q10. Dixie Construction is a young firm that is in the process of bidding (and winning) construction contracts. While they are unable to pay any dividends today, once the contracts are awarded and their work begins in earnest, they expect to be able to start paying a dividend of $2.00 per share beginning three years from now (t = 3). From that point forward, as they build their reputation and capacity, they expect to be able to increase their dividend 5.00% each year. If Dixie's cost of equity capital is 7.50% (the discount rate for equity), what price per share should their shares trade at today?** (Enter just the number in dollars without the $ sign or a comma and round off decimals to the closest integer, i.e., rounding $30.49 down to $30 and rounding $30.50 up to $31.)

Answer: 69
<details>
  <summary>Click for Solution</summary>
    
    the price per share at t = 2: $2 / (0.075 - 0.05) = $80
    move back to t = 0: P0 = PV(0.075, 2, , 80) = $69
</details>

<br>


**Q11. Viento Windmills is a utility that charges customers for their wind generated electricity. With their current technology, they earn a total of $65 million each year to pay out to their 2 million shareholders. While their geographic footprint is fixed and we can't expect the climate to get progressively windier over time, they do have an opportunity to invest in technology that will more efficiently extract the wind energy and thus produce more megawatts to sell to customers. A one-time investment one year from now (t = 1) of $37 million for a state of the art lubricant system for the windmills will lead to extra cash flows that stay constant at $17 million per year starting the following year (t = 2) and lasting forever. If Viento plans to make the investment and cost of equity capital (the discount rate for equity) is 11.0%, calculate the increase or decrease in the share price of Viento as a result of this decision. Draw time line to understand what is going on.** (Enter just the number in dollars without the $ sign or a comma and round off decimals to the closest integer, i.e., rounding $30.49 down to $30 and rounding $30.50 up to $31.)

Answer: 53
<details>
  <summary>Click for Solution</summary>
    
    the total price at t = 1: ($65 + $17) / 0.11 = $745.45 million
    the total dividend at t = 1: $65 - $37 = $28 million
    P0 (share price) after investment = ($28 + $745.45) / (1 + 0.11) / 2 = $348.40
    P0 (share price) original = $65 / 0.11 / 2 = $295.45
</details>

<br>




[^definition]: The definiton of Time Value of Money (TMV)
from [Investopedia](https://www.investopedia.com/terms/t/timevalueofmoney.asp)
[^ytm]: The definition of Yield to Maturity (YTM) from [Investopedia](https://www.investopedia.com/terms/y/yieldtomaturity.asp)