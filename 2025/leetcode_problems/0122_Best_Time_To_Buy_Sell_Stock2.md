# 122. Best Time to Buy and Sell Stock II
You are given an integer array prices where prices[i] is the price of a given stock on the ith day.

On each day, you may decide to buy and/or sell the stock. You can only hold at most one share of the stock at any time. However, you can buy it then immediately sell it on the same day.

Find and return the maximum profit you can achieve.

 

### sExample 1:
```shell
Input: prices = [7,1,5,3,6,4]
Output: 7
Explanation: Buy on day 2 (price = 1) and sell on day 3 (price = 5), profit = 5-1 = 4.
Then buy on day 4 (price = 3) and sell on day 5 (price = 6), profit = 6-3 = 3.
Total profit is 4 + 3 = 7.
```
### Example 2:
```shell
Input: prices = [1,2,3,4,5]
Output: 4
Explanation: Buy on day 1 (price = 1) and sell on day 5 (price = 5), profit = 5-1 = 4.
Total profit is 4.
```
### Example 3:
```shell
Input: prices = [7,6,4,3,1]
Output: 0
Explanation: There is no way to make a positive profit, so we never buy the stock to achieve the maximum profit of 0.
```

### Constraints:
```shell
1 <= prices.length <= 3 * 10^4
0 <= prices[i] <= 10^4
```

## Solution 1: quadratic time and linear space

```
Time complexity: O(n^2)
Space complexity: O(n)
```

```
prices = [1,500,1000,1200,1500]
loop index of i: 0, 1, 2, 3, 4
profits = [0, 499, 999, 1199, 1499]
lastMaxProfitJ = 0, 0, 0, 0, 0
```

### Pseudocode
```go
- profits := []
- maxProfit := 0
- lastMaxProfitJ := 0
- for i from 0 to len(prices) - 1:
    - for j from lastMaxProfitJ to i-1:
        - directProfit := prices[i] - prices[j]
        - indirectProfit := profits[j] + (prices[i] - prices[j+1])
        - if directProfit > profits[i]:
            - profits[i] = directProfit
        - if indirectProfit > profits[i]:
            - profits[i] = indirectProfit
        - if profits[i] > maxProfit:
            - maxProfit = profits[i]
            - lastMaxProfitJ = j
- return maxProfit
```
### Golang
```go
func maxProfit(prices []int) int {
    /* 
    profit at index i will contain the maximum of profit you can get at index either through 
     direct or indirect path.
     direct path:  prices[j] to prices[i]
     indirect path: profits[j] + (prices[i] - prices[j+1])
    */
    profits := make([]int, len(prices))
    maxProfit := 0
    /*
      till this particular j this is the maximum profic we can either direct or indirect path.
      so we don't have to check any previous indeces. Since this path already give max profit 
      whcih we can add to the indirect path of some other index i.
    */
    lastMaxProfitJ := 0
    for i:=0; i<len(prices); i++{
        // here just using j:=0 runs at ~510ms and j:=lastMaxProfitJ with ~260ms runtime
        for j:=lastMaxProfitJ; j < i; j++{
            directProfit := prices[i] - prices[j]
            indirectProfit := profits[j] + (prices[i] - prices[j+1])
            if directProfit > profits[i] {
                profits[i] = directProfit
            }
            if indirectProfit > profits[i] {
                profits[i] = indirectProfit
            }

            /* 
            Remember if you use >= then, the case [1,500,1000,1200,1500] will fail
            lastMaxProfitJ stores the last maxProfit j not the value of i.
            Even though there might be multiple paths leading to maxProfit
            the lastMaxProfitJ keeps track first path that gives maxProfit.
            */
            if profits[i] > maxProfit {
                maxProfit = profits[i]
                lastMaxProfitJ = j
            }
        }
    }
    return maxProfit
}
```


## Solution 2: linear time and constant space
***Intution:*** 
Visualize this problem as a line graph. If you find any global maximum and minimum, then that will not give you the maximum profit. Instead you can add up each of the small profits(positive slopes) in the graph. When you compute the profit for each adjacent points and add up them, then that will cover all the places where there is a possitive slope. So this will be the maximum profit that you can get.

```
Time complexity: O(n)
Space complexity: O(1)
```
### Examples:
```shell
[7,1,5,3,6,4]
i   profit  maxProfit
1   -6      0
2   4       4
3   -2      4
4   3       7
5   -2      7
```

```shell
[1,20,5,1000]
i   profit  maxProfit
1   19      19
2   -15     19
3   995     1014
```

```shell
4 1 1000 1001
i   profit  maxProfit
1   -3      0
2   999     999
3   1       1000
```

### Pseudocode
```go
- maxProfit := 0
- for i from 0 to len(pricess):
    - profit := profit[i] = profit[i-1]
    - if profit > 0
        - maxProfit = maxProfit + profit
- return maxProfit
```

### Golang
```golang
func maxProfit(prices []int) int {
    maxProfit := 0
    for i:=1; i<len(prices); i++{
        /*
        compute the profit between current index and previous index.
        add it to the maxProfit if the profit > 0.
        */
        profit := prices[i] - prices[i-1]
        if profit > 0 {
            maxProfit = maxProfit + profit
        }
    }
    return maxProfit
}
```