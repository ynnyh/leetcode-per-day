<!--
 * @Author: 月魂
 * @Date: 2021-04-04 13:52:55
 * @LastEditTime: 2021-04-04 13:53:16
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day88.md
-->
### 对角线遍历
给定一个含有 M x N 个元素的矩阵（M 行，N 列），请以对角线遍历的顺序返回这个矩阵中的所有元素，对角线遍历如下图所示。

```
var findDiagonalOrder = function(matrix) {
  // 计算所有的对角线条数 row + col - 1
  // 计算当前方向，奇数右下，偶数左上
  if (matrix.length === 0) return [];
  let m = matrix.length, n = matrix[0].length;
  let ans = [];
  for (let i = 1; i < m + n; i++) {
    let xMax = i % 2 === 0 ? m : n;
    let yMax = i % 2 === 0 ? n : m;
    for (let x = 0; x < i; x++) {
      let y = i - x - 1;
      if (x >= xMax || y >= yMax) continue;
      ans.push(i % 2 === 0 ? matrix[x][y] : matrix[y][x]);
    }
  }
  return ans;
};
```
