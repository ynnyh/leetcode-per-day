<!--
 * @Author: 月魂
 * @Date: 2021-04-13 21:11:04
 * @LastEditTime: 2021-04-13 21:11:32
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day97.md
-->
### 寻找旋转排序数组中的最小值
已知一个长度为 n 的数组，预先按照升序排列，经由 1 到 n 次 旋转 后，得到输入数组。例如，原数组 nums = [0,1,2,4,5,6,7] 在变化后可能得到：
若旋转 4 次，则可以得到 [4,5,6,7,0,1,2]
若旋转 7 次，则可以得到 [0,1,2,4,5,6,7]
注意，数组 [a[0], a[1], a[2], ..., a[n-1]] 旋转一次 的结果为数组 [a[n-1], a[0], a[1], a[2], ..., a[n-2]] 。

给你一个元素值 互不相同 的数组 nums ，它原来是一个升序排列的数组，并按上述情形进行了多次旋转。请你找出并返回数组中的 最小元素 。

链接：https://leetcode-cn.com/leetbook/read/array-and-string/c3ki5/

```
var findMin = function(nums) {
  let p1 = 0;
  let p2 = nums.length - 1;
  let ans = Infinity;
  if (nums.length === 1) return nums[0];
  while (p1 < p2) {
    if (nums[p1] > nums[p2]) {
      ans = Math.min(ans, nums[p2])
      p2--;
    } else if (nums[p1] < nums[p2]) {
      ans = Math.min(ans, nums[p1]);
      p1++;
    }
  }
  return ans;
};
```