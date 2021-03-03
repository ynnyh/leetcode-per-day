<!--
 * @Author: 月魂
 * @Date: 2021-03-03 10:26:21
 * @LastEditTime: 2021-03-03 10:27:06
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day56.md
-->
### 打家劫舍

你是一个专业的小偷，计划偷窃沿街的房屋。每间房内都藏有一定的现金，影响你偷窃的唯一制约因素就是相邻的房屋装有相互连通的防盗系统，如果两间相邻的房屋在同一晚上被小偷闯入，系统会自动报警。

给定一个代表每个房屋存放金额的非负整数数组，计算你 不触动警报装置的情况下 ，一夜之内能够偷窃到的最高金额。

链接：https://leetcode-cn.com/problems/house-robber

```
var rob = function(nums) {
  let arr = new Array(nums.length + 1);
  arr[0] = 0;
  arr[1] = nums[0];
  if (nums.length === 0) return 0;
  for (let i = 2; i <= nums.length; i++) {
    arr[i] = Math.max(arr[i - 1], arr[i - 2] + nums[i - 1]);
  }
  return arr[nums.length];
};
```