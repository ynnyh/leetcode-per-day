<!--
 * @Author: 月魂
 * @Date: 2021-03-01 22:53:13
 * @LastEditTime: 2021-03-01 22:53:50
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day54.md
-->
### 爬楼梯

假设你正在爬楼梯。需要 n 阶你才能到达楼顶。

每次你可以爬 1 或 2 个台阶。你有多少种不同的方法可以爬到楼顶呢？

注意：给定 n 是一个正整数

```
var climbStairs = function(n) {
  const dp = new Array(n + 1).fill(0);
  dp[0] = 1;
  dp[1] = 1;
  for (let i = 2; i < dp.length; i++) {
    dp[i] = dp[i - 2] + dp[i - 1];
  }
  return dp[n];
};
```
