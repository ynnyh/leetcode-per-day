<!--
 * @Author: 月魂
 * @Date: 2021-03-10 09:56:01
 * @LastEditTime: 2021-03-10 09:56:29
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day63.md
-->
### 颠倒二进制位
颠倒给定的 32 位无符号整数的二进制位。

```
var reverseBits = function(n) {
  let str = n.toString(2);
  let arr = str.split('');
  while (arr.length < 32) {
    arr.unshift('0');
  }
  return parseInt(arr.reverse().join(''), 2);
};
```