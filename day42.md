<!--
 * @Author: 月魂
 * @Date: 2021-02-17 21:14:20
 * @LastEditTime: 2021-02-17 21:14:51
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day42.md
-->
### 重塑矩阵
在MATLAB中，有一个非常有用的函数 reshape，它可以将一个矩阵重塑为另一个大小不同的新矩阵，但保留其原始数据。

给出一个由二维数组表示的矩阵，以及两个正整数r和c，分别表示想要的重构的矩阵的行数和列数。

重构后的矩阵需要将原始矩阵的所有元素以相同的行遍历顺序填充。

如果具有给定参数的reshape操作是可行且合理的，则输出新的重塑矩阵；否则，输出原始矩阵。

链接：https://leetcode-cn.com/problems/reshape-the-matrix

```
var matrixReshape = function(nums, r, c) {
  let arr = nums.flat();
  let ans = [];
  if (arr.length !== r * c) {
    return nums;
  } else {
    while (arr.length > 0) {
      ans.push(arr.splice(0, c));
    }
  }
  return ans;
};
```