<!--
 * @Author: 月魂
 * @Date: 2021-03-02 15:53:47
 * @LastEditTime: 2021-03-02 15:54:23
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day55.md
-->
### 买卖股票的最佳时机
给定一个数组 prices ，它的第 i 个元素 prices[i] 表示一支给定股票第 i 天的价格。

你只能选择 某一天 买入这只股票，并选择在 未来的某一个不同的日子 卖出该股票。设计一个算法来计算你所能获取的最大利润。

返回你可以从这笔交易中获取的最大利润。如果你不能获取任何利润，返回 0 。

链接：https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock

```
var maxProfit = function(prices) {
  let res = 0;
  let max = 0;
  for (let i = 0; i < prices.length - 1; i++) {
    res += prices[i + 1] - prices[i];
    res = res < 0 ? 0 : res;
    max = Math.max(max, res);
  }
  return max;
};
```
