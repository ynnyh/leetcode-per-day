<!--
 * @Author: 月魂
 * @Date: 2021-02-28 12:08:49
 * @LastEditTime: 2021-02-28 12:11:03
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day53.md
-->
### 单调数列
如果数组是单调递增或单调递减的，那么它是单调的。

如果对于所有 i <= j，A[i] <= A[j]，那么数组 A 是单调递增的。 如果对于所有 i <= j，A[i]> = A[j]，那么数组 A 是单调递减的。

当给定的数组 A 是单调数组时返回 true，否则返回 false。

链接：https://leetcode-cn.com/problems/monotonic-array

```
var isMonotonic = function(A) {
  let p = 0;
  let flag = '';
  while (p < A.length) {
    if (A[p] > A[p + 1]) {
      if (flag !== '' && flag === '-') return false;
      flag = '+';
    } else if (A[p] < A[p + 1]) {
      if (flag !== '' && flag === '+') return false;
      flag = '-';
    }
    p++;
  }
  return true;
};
```