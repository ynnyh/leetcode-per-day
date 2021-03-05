<!--
 * @Author: 月魂
 * @Date: 2021-03-05 16:49:02
 * @LastEditTime: 2021-03-05 16:50:06
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day58.md
-->
### 计数质数
统计所有小于非负整数 n 的质数的数量。

```
var countPrimes = function(n) {
  function isPrime(x) {
    for(let i = 2; i * i <= x; i++) {
      if (x % i === 0) {
        return false;
      }
    }
    return true;
  }
  let ans = 0;
  for (let i = 2; i < n; i++) {
    ans += isPrime(i);
  }
  return ans;
};
```