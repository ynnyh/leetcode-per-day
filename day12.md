<!--
 * @Author: 月魂
 * @Date: 2021-01-18 19:29:24
 * @LastEditTime: 2021-01-18 19:29:56
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day12.md
-->

### 反转字符串
编写一个函数，其作用是将输入的字符串反转过来。输入字符串以字符数组 char[] 的形式给出。

不要给另外的数组分配额外的空间，你必须原地修改输入数组、使用 O(1) 的额外空间解决这一问题。

你可以假设数组中的所有字符都是 ASCII 码表中的可打印字符。

链接：https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/xnhbqj/

```
var reverseString = function(s) {
  let p1 = 0;
  let p2 = s.length - 1;
  while (p1 < p2) {
    [s[p1], s[p2]] = [s[p2], s[p1]];
    p1++;
    p2--;
  }
};
```