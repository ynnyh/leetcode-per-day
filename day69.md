<!--
 * @Author: 月魂
 * @Date: 2021-03-16 18:25:16
 * @LastEditTime: 2021-03-16 18:26:12
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day69.md
-->
### 螺旋矩阵 II
给你一个正整数 n ，生成一个包含 1 到 n2 所有元素，且元素按顺时针顺序螺旋排列的 n x n 正方形矩阵 matrix 。

```
 let num1 = 1;
  let top = 0, left = 0;
  let bottom = n - 1, right = n - 1;
  let ans = [];
  for (let i = 0; i < n; i++) {
    ans.push([]);
  }
  while (top < bottom && left < right) {
    for (let i = left; i < right; i++) { // top
      ans[top][i] = num1;
      num1++;
    }
    for (let i = top; i < bottom; i++) { // right
      ans[i][right] = num1;
      num1++;
    }
    for (let i = right; i > left; i--) { // bottom
      ans[bottom][i] = num1;
      num1++;
    }
    for (let i = bottom; i > top; i--) { // left
      ans[i][left] = num1;
      num1++;
    }
    top++;
    left++;
    right--;
    bottom--;
  }
  if (top === bottom) {
    for (let i = left; i <= right; i++) {
      ans[top][i] = num1;
      num1++;
    }
  } else if (left === right) {
    for (let i = top; i <= bottom; i++) {
      ans[i][left] = num1;
      num1++;
    }
  }
  return ans;
};
```