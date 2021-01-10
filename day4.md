### 旋转数组
给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。

链接：https://leetcode-cn.com/problems/rotate-array

```
// 解法1
var rotate = function(nums, k) {
  for(let i = 0; i < k; i++) {
    nums.unshift(nums.pop());
  }
  return nums;
};
// 解法2
var rotate = function(nums, k) {
  let arr = nums.splice(nums.length - k);
  nums.splice(0, 0, ...arr);
};
```