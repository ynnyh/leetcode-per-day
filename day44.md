<!--
 * @Author: 月魂
 * @Date: 2021-02-19 10:24:15
 * @LastEditTime: 2021-02-19 10:24:45
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day44.md
-->
### 最大连续1的个数 III
给定一个由若干 0 和 1 组成的数组 A，我们最多可以将 K 个值从 0 变成 1 。

返回仅包含 1 的最长（连续）子数组的长度。

```
var longestOnes = function(A, K) {
  let left = 0;
  let right = 0;
  let max = 0;
  let count = K;
  while (right < A.length) {
    if (A[right] === 0 && K > 0) {
      right++;
      K--;
    } else if (A[right] === 1) {
      right++;
    } else {
      max = Math.max(max, right - left);
      if (A[left] === 0) {
        right++;
      }
      left++;
    }
  }
  return Math.max(max, right - left);
};
```