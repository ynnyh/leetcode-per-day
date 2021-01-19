<!--
 * @Author: 月魂
 * @Date: 2021-01-19 21:38:16
 * @LastEditTime: 2021-01-19 21:39:12
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day13.md
-->

### 整数反转

给出一个 32 位的有符号整数，你需要将这个整数中每位上的数字进行反转。

```
var reverse = function(x) {
  let y = Math.abs(x)
  let num = 0;
  while (y > 0) {
    num = num * 10 + y % 10;
    y = Math.floor(y / 10);
  }
  if (x < 0) {
    return num <= Math.pow(2, 31) ? -num : 0;
  } else {
    return num < Math.pow(2, 31) ? num : 0;
  }
};
```
