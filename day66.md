<!--
 * @Author: 月魂
 * @Date: 2021-03-12 17:59:02
 * @LastEditTime: 2021-03-12 18:02:41
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day66.md
-->
### 缺失数字
给定一个包含 [0, n] 中 n 个数的数组 nums ，找出 [0, n] 这个范围内没有出现在数组中的那个数。

```
// 第一种解法
var missingNumber = function(nums) {
  let s = new Set();
  let arr = [];
  for (let i = 0; i <= nums.length; i++) {
    arr.push(i);
  }
  for (let i = 0; i < nums.length; i++) {
    s.add(nums[i]);
  }
  for (let i = 0; i < arr.length; i++) {
    if (!s.has(arr[i])) return arr[i];
  }
};
// 第二种解法
var missingNumber = function(nums) {
  nums.sort((a, b) => a - b);
  for (let i = 0; i <= nums.length; i++) {
    if (i !== nums[i]) return i;
  }
};
```
