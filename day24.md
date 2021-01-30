<!--
 * @Author: 月魂
 * @Date: 2021-01-30 21:54:41
 * @LastEditTime: 2021-01-30 21:55:13
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day24.md
-->

### 三数之和
给你一个包含 n 个整数的数组 nums，判断 nums 中是否存在三个元素 a，b，c ，使得 a + b + c = 0 ？请你找出所有和为 0 且不重复的三元组。

注意：答案中不可以包含重复的三元组。

链接：https://leetcode-cn.com/problems/3sum

```
var threeSum = function(nums) {
  let ans = [];
  const length = nums.length;
  if (nums === null || length < 3) return ans;
  let arr = nums.sort((a, b) => a- b);
  let p1 = 0;
  while (p1 < length) {
    if (arr[p1] > 0) break;
    if (p1 > 0 && arr[p1] === arr[p1 - 1]) {
      p1++;
      continue;
    }
    let L = p1 + 1;
    let R = length - 1;
    while (L < R) {
      let res = arr[p1] + arr[L] + arr[R];
      if (res === 0) {
        ans.push([arr[p1], arr[L], arr[R]]);
        while (L < R && arr[L] === arr[L + 1]) {
          L++;
        }
        while (L < R && arr[R] === arr[R - 1]) {
          R--;
        }
        L++;
        R--;
      } else if (res < 0) {
        L++;
      } else if (res > 0) {
        R--;
      }
    }
    p1++;
  }
  return ans;
};
```