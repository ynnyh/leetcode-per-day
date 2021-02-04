<!--
 * @Author: 月魂
 * @Date: 2021-02-04 19:34:04
 * @LastEditTime: 2021-02-04 19:34:32
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day29.md
-->
### 子数组最大平均数 I
给定 n 个整数，找出平均数最大且长度为 k 的连续子数组，并输出该最大平均数。

```
var findMaxAverage = function(nums, k) {
  let ans = 0;
  let sum = 0;
  for (let i = 0; i < k; i++) {
    sum += nums[i];
  }
  let newSum = sum;
  for (let i = k; i < nums.length; i++) {
    sum = sum - nums[i - k] + nums[i];
    newSum = Math.max(sum, newSum);
  }
  ans = newSum / k;
  return ans;
};
```
