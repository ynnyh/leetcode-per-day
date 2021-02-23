<!--
 * @Author: 月魂
 * @Date: 2021-02-23 14:36:42
 * @LastEditTime: 2021-02-23 14:37:19
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day48.md
-->
### 爱生气的书店老板
今天，书店老板有一家店打算试营业 customers.length 分钟。每分钟都有一些顾客（customers[i]）会进入书店，所有这些顾客都会在那一分钟结束后离开。

在某些时候，书店老板会生气。 如果书店老板在第 i 分钟生气，那么 grumpy[i] = 1，否则 grumpy[i] = 0。 当书店老板生气时，那一分钟的顾客就会不满意，不生气则他们是满意的。

书店老板知道一个秘密技巧，能抑制自己的情绪，可以让自己连续 X 分钟不生气，但却只能使用一次。

请你返回这一天营业下来，最多有多少客户能够感到满意的数量。

链接：https://leetcode-cn.com/problems/grumpy-bookstore-owner

```
var maxSatisfied = function(customers, grumpy, X) {
  let ans = 0;
  let max = 0;
  let sum = 0;
  let right = 0;
  let left = 0;
  while (right < customers.length) {
    sum += grumpy[right] ? customers[right] : 0;
    ans += grumpy[right] ? 0 : customers[right];
    if (right - left + 1 > X) {
      sum -= grumpy[left] ? customers[left] : 0;
      left++;
    }
    right++;
    max = Math.max(max, sum);
  }
  return ans + max;
};
```