<!--
 * @Author: 月魂
 * @Date: 2021-02-15 15:49:56
 * @LastEditTime: 2021-02-15 15:50:27
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day40.md
-->
### 最大连续1的个数
给定一个二进制数组， 计算其中最大连续1的个数。

```
var findMaxConsecutiveOnes = function(nums) {
  let left = 0;
  let count = 0;
  let ans = count;
  while(left < nums.length) {
    if (nums[left] === 1) {
      count++;
      ans = Math.max(ans, count);
      left++;
    } else {
      count = 0;
      left++;
    }
  }
  return ans;
};
```
