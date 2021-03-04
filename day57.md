<!--
 * @Author: 月魂
 * @Date: 2021-03-04 11:06:20
 * @LastEditTime: 2021-03-04 11:06:53
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day57.md
-->
### Fizz Buzz
写一个程序，输出从 1 到 n 数字的字符串表示。

1. 如果 n 是3的倍数，输出“Fizz”；

2. 如果 n 是5的倍数，输出“Buzz”；

3.如果 n 同时是3和5的倍数，输出 “FizzBuzz”。

链接：https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/xngt85/

```
var fizzBuzz = function(n) {
  let ans = [];
  for (let i = 1; i <= n; i++) {
    if (i % 3 === 0 && i % 5 === 0) {
      ans.push('FizzBuzz');
    } else if (i % 3 === 0) {
      ans.push('Fizz');
    } else if (i % 5 === 0) {
      ans.push('Buzz');
    } else {
      ans.push(i + '');
    }
  }
  return ans;
};
```