<!--
 * @Author: 月魂
 * @Date: 2021-02-22 10:05:27
 * @LastEditTime: 2021-02-22 10:06:31
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day47.md
-->
### 托普利茨矩阵
给你一个 m x n 的矩阵 matrix 。如果这个矩阵是托普利茨矩阵，返回 true ；否则，返回 false 。

如果矩阵上每一条由左上到右下的对角线上的元素都相同，那么这个矩阵是 托普利茨矩阵 。

链接：https://leetcode-cn.com/problems/toeplitz-matrix

```
// 第一种解法
var isToeplitzMatrix = function(matrix) {
  let ans = true;
  for (let i = 0; i < matrix.length; i++) {
    for (let j = 0; j < matrix[i].length; j++) {
      if (matrix[i - 1] && j - 1 >= 0) {
        if (matrix[i - 1][j - 1] === matrix[i][j]) {
          ans = true;
        } else {
          ans = false;
          return ans;
        }
      }
    }
  }
  return ans;
};

// 第二种解法
var isToeplitzMatrix = function(matrix) {
  let f = matrix.length;
  let s = matrix[0].length;
  for (let i = 1; i < f; i++) {
    for (let j = 1; j < s; j++) {
      if (matrix[i][j] !== matrix[i - 1][j - 1]) {
        return false;
      }
    }
  }
  return true;
};
```