<!--
 * @Author: 月魂
 * @Date: 2021-04-06 13:53:07
 * @LastEditTime: 2021-04-06 13:53:27
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day90.md
-->
### 删除有序数组中的重复项 II
给你一个有序数组 nums ，请你 原地 删除重复出现的元素，使每个元素 最多出现两次 ，返回删除后数组的新长度。

不要使用额外的数组空间，你必须在 原地 修改输入数组 并在使用 O(1) 额外空间的条件下完成。

链接：https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array-ii

```
var removeDuplicates = function(nums) {
  if (nums.length === 0) return 0;
  let num = 1;
  let p = 1;
  let prev = nums[0];
  while (p < nums.length) {
    if (prev === nums[p]) {
      if (num < 2) {
        num++;
        p++;
      } else {
        nums.splice(p, 1);
      }
    } else {
      prev = nums[p];
      p++;
      num = 1;
    }
  }
  return nums.length;
};
```