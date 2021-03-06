<!--
 * @Author: 月魂
 * @Date: 2021-03-06 18:35:16
 * @LastEditTime: 2021-03-06 18:35:40
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day59.md
-->
### 3的幂
给定一个整数，写一个函数来判断它是否是 3 的幂次方。如果是，返回 true ；否则，返回 false 。

整数 n 是 3 的幂次方需满足：存在整数 x 使得 n == 3x

链接：https://leetcode-cn.com/problems/power-of-three

```
var isPowerOfThree = function(n) {
  function isThree(x) {
    while (x > 1) {
      x /= 3;
    }
    if (x === 1) return true;
    return false;
  }
  return isThree(n);
};
```