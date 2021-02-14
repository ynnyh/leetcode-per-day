<!--
 * @Author: 月魂
 * @Date: 2021-02-14 19:22:16
 * @LastEditTime: 2021-02-14 19:23:09
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day39.md
-->
### 最大子序和
给定一个整数数组 nums ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。

```
var maxSubArray = function(nums) {
  let pre = 0;
  let ans = nums[0];
  nums.forEach(num => {
    pre = Math.max(pre + num, num);
    ans = Math.max(ans, pre);
  })
  return ans;
};
```
