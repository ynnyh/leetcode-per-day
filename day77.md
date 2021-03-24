<!--
 * @Author: 月魂
 * @Date: 2021-03-24 16:59:57
 * @LastEditTime: 2021-03-24 17:00:15
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day77.md
-->
### 拥有最多糖果的孩子
给你一个数组 candies 和一个整数 extraCandies ，其中 candies[i] 代表第 i 个孩子拥有的糖果数目。

对每一个孩子，检查是否存在一种方案，将额外的 extraCandies 个糖果分配给孩子们之后，此孩子有 最多 的糖果。注意，允许有多个孩子同时拥有 最多 的糖果数目。

链接：https://leetcode-cn.com/problems/kids-with-the-greatest-number-of-candies

```
var kidsWithCandies = function(candies, extraCandies) {
  let max = 0;
  let ans = [];
  for (let i = 0; i < candies.length; i++) {
    if (candies[i] > max) {
      max = candies[i];
    }
  }
  for (let i = 0; i < candies.length; i++) {
    if (candies[i] + extraCandies >= max) {
      ans.push(true);
    } else {
      ans.push(false);
    }
  }
  return ans;
};
```