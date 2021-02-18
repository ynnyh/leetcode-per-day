<!--
 * @Author: 月魂
 * @Date: 2021-02-18 09:35:59
 * @LastEditTime: 2021-02-18 09:36:33
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day43.md
-->
### 最富有客户的资产总量
给你一个 m x n 的整数网格 accounts ，其中 accounts[i][j] 是第 i​​​​​​​​​​​​ 位客户在第 j 家银行托管的资产数量。返回最富有客户所拥有的 资产总量 。

客户的 资产总量 就是他们在各家银行托管的资产数量之和。最富有客户就是 资产总量 最大的客户。

链接：https://leetcode-cn.com/problems/richest-customer-wealth

```
var maximumWealth = function(accounts) {
  let p = 0;
  let ans = 0;
  let sum = ans;
  while (p < accounts.length) {
    sum = accounts[p].reduce((now, next) => now + next);
    ans = Math.max(ans, sum);
    p++;
  }
  return ans;
};
```