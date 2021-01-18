<!--
 * @Author: 月魂
 * @Date: 2021-01-11 20:03:08
 * @LastEditTime: 2021-01-17 17:48:21
 * @LastEditors: 月魂
 * @Description:
 * @FilePath: \leetcode-per-day\day5.md
-->
### 存在重复元素

给定一个整数数组，判断是否存在重复元素。

如果存在一值在数组中出现至少两次，函数返回 true 。如果数组中每个元素都不相同，则返回 false 。

链接：https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/x248f5/

```
// 我的解法
var containsDuplicate = function(nums) {
  while (nums.length > 0) {
    const fir = nums.shift();
    if (nums.findIndex(item => item === fir) !== -1) return true;
  }
  return false;
};

// 排序 
/*
在对数字从小到大排序之后，数组的重复元素一定出现在相邻位置中。因此，我们可以扫描已排序的数组，每次判断相邻的两个元素是否相等，如果相等则说明存在重复的元素。
*/
var containsDuplicate = function(nums) {
  nums.sort((a, b) => a - b);
  for(let i = 0; i < nums.length - 1; i++) {
    if (nums[i] === nums[i + 1]) return true;
  }
  return false;
};

// 哈希表
/*
对于数组中每个元素，我们将它插入到哈希表中。如果插入一个元素时发现该元素已经存在于哈希表中，则说明存在重复的元素。
*/
var containsDuplicate = function(nums) {
  let s = new Set();
  for (const val of nums) {
    if (s.has(val)) return true;
    s.add(val);
  }
  return false;
};
```