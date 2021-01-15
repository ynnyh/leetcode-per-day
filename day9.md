### 移动零
给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。

```
var moveZeroes = function(nums) {
  let p1 = 0; // 快
  let p2 = 0; // 慢
  while (p1 < nums.length) {
    if (nums[p2] === 0) {
      nums.splice(p2, 1);
      nums.push(0);
    } else {
      p2++;
    }
    p1++;
  }
  return nums;
};
```