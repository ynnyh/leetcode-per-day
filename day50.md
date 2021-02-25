<!--
 * @Author: 月魂
 * @Date: 2021-02-25 15:27:13
 * @LastEditTime: 2021-02-25 15:27:37
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day50.md
-->
### 转置矩阵
给你一个二维整数数组 matrix， 返回 matrix 的 转置矩阵 。

矩阵的 转置 是指将矩阵的主对角线翻转，交换矩阵的行索引与列索引。

```
var transpose = function(matrix) {
  let n = matrix[0].length;
  let p1 = 0;
  let p2 = 0;
  let ans = [];
  while (p1 < matrix.length) {
    while (p2 < n) {
      if (!ans[p2]) {
        ans[p2] = [];
      }
      ans[p2].push(matrix[p1][p2]);
      p2++;
    }
    if (p2 === n) {
      p1++;
      p2 = 0;
    }
  }
  return ans;
};
```
