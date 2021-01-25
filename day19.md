<!--
 * @Author: 月魂
 * @Date: 2021-01-25 21:55:13
 * @LastEditTime: 2021-01-25 21:55:59
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day19.md
-->

### 外观数列
给定一个正整数 n ，输出外观数列的第 n 项。

「外观数列」是一个整数序列，从数字 1 开始，序列中的每一项都是对前一项的描述。

你可以将其视作是由递归公式定义的数字字符串序列：

countAndSay(1) = "1"
countAndSay(n) 是对 countAndSay(n-1) 的描述，然后转换成另一个数字字符串。

链接：https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/xnpvdm/


```
var countAndSay = function(n) {
  if (n === 1) {
    return '1';
  }
  let str = countAndSay(n - 1);
  let count = 1;
  let final = '';
  for (let i = 0; i < str.length; i++) {
    if (str[i] === str[i + 1]) {
      count++;
    } else {
      final += '' + count + str[i];
      count = 1;
    }
  }
  return final;
};
```