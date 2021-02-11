<!--
 * @Author: 月魂
 * @Date: 2021-02-11 16:08:47
 * @LastEditTime: 2021-02-11 16:09:53
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day36.md
-->
### 下一个排列
##### 尤为困难，还需理解
实现获取 下一个排列 的函数，算法需要将给定数字序列重新排列成字典序中下一个更大的排列。

如果不存在下一个更大的排列，则将数字重新排列成最小的排列（即升序排列）。

必须 原地 修改，只允许使用额外常数空间。

链接：https://leetcode-cn.com/problems/next-permutation

```
var nextPermutation = function(nums) {
  let i = nums.length - 2;
  while (i >= 0 && nums[i] >= nums[i + 1]) {
    i--;
  }
  if (i >= 0) {
    let j = nums.length - 1;
    while(j >= 0 && nums[j] <= nums[i]) {
      j--;
    }
    [nums[i], nums[j]] = [nums[j], nums[i]];
  }
  let L = i + 1;
  let R = nums.length - 1;
  while(L < R) {
    [nums[L], nums[R]] = [nums[R], nums[L]];
    L++;
    R--;
  }
};
```