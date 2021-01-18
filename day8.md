<!--
 * @Author: 月魂
 * @Date: 2021-01-14 21:43:32
 * @LastEditTime: 2021-01-17 17:48:58
 * @LastEditors: 月魂
 * @Description:
 * @FilePath: \leetcode-per-day\day8.md
-->
### 加一
给定一个由 整数 组成的 非空 数组所表示的非负整数，在该数的基础上加一。

最高位数字存放在数组的首位， 数组中每个元素只存储单个数字。

你可以假设除了整数 0 之外，这个整数不会以零开头。

链接：https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/x2cv1c/

```
// 我的解法
// 在使用Number类型时出现问题，超过范围
var plusOne = function(digits) {
  let arr = [];
  if (digits.length === 1) {
    let num = digits.join('') * 1;
    num = num + 1 + '';
    return num.split('');
  } else {
    if (digits[0] === 0) {
      while (digits[0] === 0 && digits.length > 1) {
        arr.push(0);
        digits.splice(0, 1);
      }
    }
    let num = BigInt(digits.join(''));
    num = num + 1n + '';
    let newA = num.split('');
    newA.splice(0, 0, ...arr);
    return newA;
  }
  
};
```