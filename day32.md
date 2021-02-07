<!--
 * @Author: 月魂
 * @Date: 2021-02-07 20:39:10
 * @LastEditTime: 2021-02-07 20:39:37
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day32.md
-->
### 非递减数列
给你一个长度为 n 的整数数组，请你判断在 最多 改变 1 个元素的情况下，该数组能否变成一个非递减数列。

我们是这样定义一个非递减数列的： 对于数组中所有的 i (0 <= i <= n-2)，总满足 nums[i] <= nums[i + 1]。



链接：https://leetcode-cn.com/problems/non-decreasing-array

```
var checkPossibility = function(nums) {
  let count = 0;
  let p = 0;
  while(p < nums.length) {
    if (nums[p] > nums[p + 1]) {
      if (nums[p - 1] > nums[p + 1]) {
        nums[p + 1] = nums[p];
      } else {
        nums[p] = nums[p - 1];
      }
      count ++;
      if (count > 1) return false;
    }
    p++;
  }
  return count <= 1;
};
```