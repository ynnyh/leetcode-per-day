<!--
 * @Author: 月魂
 * @Date: 2021-03-09 10:29:42
 * @LastEditTime: 2021-03-09 10:30:28
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day62.md
-->
### 汉明距离
两个整数之间的汉明距离指的是这两个数字对应二进制位不同的位置的数目。

给出两个整数 x 和 y，计算它们之间的汉明距离。

注意：
0 ≤ x, y < 231.

链接：https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/xnyode/

```
var hammingDistance = function(x, y) {
  let num = 0;
  while (x >= 1 || y >= 1) {
    // 存在x或y已经等于1的极端情况
    if (x >= 1 && y === 0) {
      // 对x进行换算
      while (x >= 1) {
        if (x % 2 === 1) {
          num += 1;
        }
        x = Math.floor(x / 2);
      }
    } else if (x === 0 && y >= 1) {
      // 对y进行换算
      while (y >= 1) {
        if (y % 2 === 1) {
          num += 1;
        }
        y = Math.floor(y / 2);
      }
    } else if (x >= 1 && y >= 1) {
      if (x % 2 === y % 2) {
      } else {
        num += 1;
      }
      x = Math.floor(x / 2);
      y = Math.floor(y / 2);
    }
  }
  return num;
};
```