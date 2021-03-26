<!--
 * @Author: 月魂
 * @Date: 2021-03-26 13:32:37
 * @LastEditTime: 2021-03-26 13:32:54
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day79.md
-->
### 重新排列数组
给你一个数组 nums ，数组中有 2n 个元素，按 [x1,x2,...,xn,y1,y2,...,yn] 的格式排列。

请你将数组按 [x1,y1,x2,y2,...,xn,yn] 格式重新排列，返回重排后的数组。

链接：https://leetcode-cn.com/problems/shuffle-the-array

```
var shuffle = function(nums, n) {
  let ans = [];
  for (let i = 0; i < n; i++) {
    ans.push(nums[i]);
    ans.push(nums[n + i]);
  }
  return ans;
};
```