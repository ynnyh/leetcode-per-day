<!--
 * @Author: 月魂
 * @Date: 2021-03-29 15:08:06
 * @LastEditTime: 2021-03-29 15:08:27
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day82.md
-->
### 颠倒二进制位
颠倒给定的 32 位无符号整数的二进制位。

```
var reverseBits = function(n) {
  let str = n.toString(2);
  let arr = str.split('').reverse();
  return parseInt(arr.join('').padEnd(32, 0), 2);
};
```