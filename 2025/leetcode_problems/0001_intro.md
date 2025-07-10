# LeetCode

## Language Choice(Rust)

- Initially I started solvig these problems using Golang because it is simple and yet powerful. But later switched to Rust language because it is more `secure`, `not garbage collected`(using `ownerships` and `lifetimes`), has compile time advantages(`macros`, `error handling`) and mainly it is `fully community backed`(like PostgreSQL).



This section contains my solution for Leetcode problems. `All these questions are created and provided by Leetcode and I have no rights to those problems`. I am just sharing these solutions so that it might be helpful to someone.

Source - [LeetCode](https://leetcode.com/problems/)

# Overview of problems

### 26. Remove Duplicates from Sorted Array
- used visitedMap to keep track of already seen element and separate k index where i<=k are all unique.
- [link](./0026_Remove_Duplicates_From_Sorted_Array.md)


### 27. Remove Element
- element's index < k are valid elements. increment k only when next valid element is moved to position i
- [link](./0027_Remove_Element.md)

### 121. Best Time to Buy and Sell Stock
- Here we can buy and sell at most one stock. As index progresses update the current min. find the profit using current value and current min. if the profit is greater than maxProfit then update this value to the maxProfit
- [link](./0121_Best_Time_To_Buy_Sell_Stock.md)

### 122. Best Time to Buy and Sell Stock II
- Here we can buy and sell multiple stocks but hold at most one at a time. For each index find the profit from previous index. if the values is greater than 0 then add it to the maxProfit.
- [link](./0122_Best_Time_To_Buy_Sell_Stock2.md)

### 55. Jump Game
- This solution is simple and straightforward using greedy approach. Choosing the best available option at the point.
- [link](./0055_Jump_Game.md)

