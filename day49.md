<!--
 * @Author: 月魂
 * @Date: 2021-02-24 09:40:25
 * @LastEditTime: 2021-02-24 09:41:21
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day49.md
-->
### 翻转图像
给定一个二进制矩阵 A，我们想先水平翻转图像，然后反转图像并返回结果。

水平翻转图片就是将图片的每一行都进行翻转，即逆序。例如，水平翻转 [1, 1, 0] 的结果是 [0, 1, 1]。

反转图片的意思是图片中的 0 全部被 1 替换， 1 全部被 0 替换。例如，反转 [0, 1, 1] 的结果是 [1, 0, 0]。

链接：https://leetcode-cn.com/problems/flipping-an-image

```
var flipAndInvertImage = function(A) {
  A.map(item => item.reverse());
  for (let i = 0; i < A.length; i++) {
    for (let j = 0; j < A[i].length; j++) {
      A[i][j] = A[i][j] ? 0 : 1;
    }
  }
  return A;
};
```