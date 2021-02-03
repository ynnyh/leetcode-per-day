<!--
 * @Author: 月魂
 * @Date: 2021-02-03 20:02:09
 * @LastEditTime: 2021-02-03 20:02:42
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day28.md
-->

### 搜索插入位置
给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组中，返回它将会被按顺序插入的位置。

```
var searchInsert = function(nums, target) {
  let p = 0;
  while (p < nums.length) {
    if (nums[p] < target) {
      p++;
    } else {
      return p;
    }
  }
  return p;
};
```
