# guoxinfe-FOF-dressing-invisible-and-matching

This is a project focusing on the factors regarding Fund of Fund(FOF). By calculating the dressing, invisible, and matching factors, we can evaluate the performance of certain funds. Here we use funds that trade mainly on stocks.

Due to some confidentiality concern, the data and the original journal is not posted, but the types of data and the construction of factors are clearly illustrated. Follow the readme file and my report, you will be able to do the replication and have a deeper understanding of FOF.

In this case we only consider the Chinese Ashare stocks.

## V1.0 The Orignal Version 

What we need are the holdings of the funds（quarterly）, the return rate of all stocks in the market(daily), and the return rate of the funds(monthly).

* First, the return rate of stocks should be calculated within certain period of time. Then it should be ranked (top50%--ascending, and bottom50% descending)
* Second, the holdings of the funds can be viewed as matrix. Stocks are to be ranked by the weight of the holding in a fund's portfolio. That is to say, if fund A and B have one stock, the weight of the stock in A is 10% while 5% in B. Then follow the rank method in the above bullet point and turn them into quantile form. Sum the numbers up and do a linear mapping in a single fund, and you will get the stuct factor, which will be used later.
* Third, calculate the return rate of the funds and minus the corresponding stuct factor, you will get the dressing/invisible factor.
* Last, by standardizing the two factors and calculate the mean of them, you will have the matching factor.

After construction of the factors, RankIC can be tested.

## V2.0 Adding Some Personal Thoughts

From the above description we can see that the ranking procedure is complicated. Is there any potential improvement that can both maintain the efficiency and simplify the calculation?
