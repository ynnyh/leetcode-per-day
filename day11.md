<!--
 * @Author: 月魂
 * @Date: 2021-01-17 17:47:25
 * @LastEditTime: 2021-01-17 17:50:15
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day11.md
-->

### 旋转图像
给定一个 n × n 的二维矩阵表示一个图像。

将图像顺时针旋转 90 度。

链接： https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/xnhhkv/

```
// 我的解法
var rotate = function(matrix) {
  let p1 = 0;
  let p2 = matrix.length - 1;
  while(p1 < matrix.length) {
    if (p2 < 0) {
      p1++;
      p2 = matrix.length - 1;
    } else {
      matrix[p1].push(matrix[p2][0]);
      matrix[p2].shift();
      p2--;
    }
  }
  return matrix;
};
```
