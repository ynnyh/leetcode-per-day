<!--
 * @Author: 月魂
 * @Date: 2021-01-31 19:42:57
 * @LastEditTime: 2021-01-31 19:44:02
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day25.md
-->

### 移除元素
给你一个数组 nums 和一个值 val，你需要 原地 移除所有数值等于 val 的元素，并返回移除后数组的新长度。

不要使用额外的数组空间，你必须仅使用 O(1) 额外空间并 原地 修改输入数组。

元素的顺序可以改变。你不需要考虑数组中超出新长度后面的元素。

链接：https://leetcode-cn.com/problems/remove-element

```
var removeElement = function(nums, val) {
  let p = 0;
  while (p < nums.length) {
    if (nums[p] === val) {
      nums.splice(p, 1);
    } else {
      p++;
    }
  }
  return p;
};
```