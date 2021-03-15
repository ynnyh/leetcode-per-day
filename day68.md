<!--
 * @Author: 月魂
 * @Date: 2021-03-15 11:20:43
 * @LastEditTime: 2021-03-15 11:21:03
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day68.md
-->
### 螺旋矩阵
给你一个 m 行 n 列的矩阵 matrix ，请按照 顺时针螺旋顺序 ，返回矩阵中的所有元素。

```
var spiralOrder = function(matrix) {
  if (matrix.length === 0) return [];
  let ans = [];
  let top = 0, left = 0;
  let bottom = matrix.length - 1;
  let right = matrix[0].length - 1;
  while (top < bottom && left < right) {
    for (let i = left; i < right; i++) {
      ans.push(matrix[top][i]); // top
    }
    for (let i = top; i < bottom; i++) {
      ans.push(matrix[i][right]); // right
    }
    for (let i = right; i > left; i--) {
      ans.push(matrix[bottom][i]); // bottom
    }
    for (let i = bottom; i > top; i--) {
      ans.push(matrix[i][left]); // left
    }
    top++;
    left++;
    right--;
    bottom--;
  }
  if (top === bottom) {
    for (let i = left; i <= right; i++) {
      ans.push(matrix[top][i]);
    }
  } else if (left === right) {
    for (let i = top; i <= bottom; i++) {
      ans.push(matrix[i][left]);
    }
  }
  return ans;
};

```