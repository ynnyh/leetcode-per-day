<!--
 * @Author: 月魂
 * @Date: 2021-04-09 17:53:33
 * @LastEditTime: 2021-04-09 17:53:52
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day93.md
-->
### 长度最小的子数组
给定一个含有 n 个正整数的数组和一个正整数 target 。

找出该数组中满足其和 ≥ target 的长度最小的 连续子数组 [numsl, numsl+1, ..., numsr-1, numsr] ，并返回其长度。如果不存在符合条件的子数组，返回 0 。

链接：https://leetcode-cn.com/problems/minimum-size-subarray-sum

```
var minSubArrayLen = function(target, nums) {
  let p1 = 0;
  let p2 = 0;
  let sum = 0;
  let ans = nums.length + 1;
  while (p2 < nums.length) {
    sum += nums[p2];
    while (sum >= target) {
      ans = Math.min(ans, p2 - p1 + 1);
      sum -= nums[p1];
      p1++;
    }
    p2++;
  }
  return ans > nums.length ? 0 : ans;
};
```