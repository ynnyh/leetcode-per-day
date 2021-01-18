<!--
 * @Author: 月魂
 * @Date: 2021-01-07 22:57:15
 * @LastEditTime: 2021-01-17 17:47:35
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day1.md
-->
### 删除排序数组中的重复项
给定一个排序数组，你需要在 原地 删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。
不要使用额外的数组空间，你必须在 原地 修改输入数组 并在使用 O(1) 额外空间的条件下完成。

链接：https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/x2gy9m

```
// 解题思路：快慢指针
var removeDuplicates = function(nums) {
  let p1 = 0;
  let p2 = 0;
  while (p2 < nums.length) {
    if (nums[p1] !== nums[p2]) {
      p1++;
      nums[p1] = nums[p2]
    }
    p2++;
  }
  return p1 + 1;
};
```