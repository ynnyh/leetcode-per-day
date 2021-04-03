<!--
 * @Author: 月魂
 * @Date: 2021-04-03 17:36:48
 * @LastEditTime: 2021-04-03 17:37:25
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day87.md
-->
### 零矩阵
编写一种算法，若M × N矩阵中某个元素为0，则将其所在的行与列清零。

```
var setZeroes = function(matrix) {
  let m = matrix.length;
  let n = matrix[0].length;
  let row = new Array(m).fill(false);
  let col = new Array(n).fill(false);
  for (let i = 0; i < m; i++) {
    for (let j = 0; j < n; j++) {
      if (matrix[i][j] === 0) {
        row[i] = col[j] = true;
      }
    }
  }
  for (let i = 0; i < m; i++) {
    for (let j = 0; j < n; j++) {
      if (row[i] || col[j]) {
        matrix[i][j] = 0;
      }
    }
  }
};
```
