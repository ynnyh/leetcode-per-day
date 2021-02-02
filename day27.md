<!--
 * @Author: 月魂
 * @Date: 2021-02-02 21:04:52
 * @LastEditTime: 2021-02-02 21:05:27
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day27.md
-->
### 最接近的三数之和
给定一个包括 n 个整数的数组 nums 和 一个目标值 target。找出 nums 中的三个整数，使得它们的和与 target 最接近。返回这三个数的和。假定每组输入只存在唯一答案。

链接：https://leetcode-cn.com/problems/3sum-closest

```
var threeSumClosest = function(nums, target) {
  nums.sort((a, b) => a - b);
  let p = 0;
  let min = nums[0] + nums[1] + nums[nums.length - 1];
  while(p < nums.length - 2) {
    let L = p + 1;
    let R = nums.length - 1;
    while(L < R) {
      let res =  nums[p] + nums[L] + nums[R];
      if (Math.abs(res - target) < Math.abs(min - target)) {
        min = res;
      }else if (res > target) {
        R--;
      } else if (res < target) {
        L++;
      } else if (res === target) {
        break;
      }
    }
    p++;
  }
  return min;
};
```