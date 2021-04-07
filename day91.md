<!--
 * @Author: 月魂
 * @Date: 2021-04-07 20:44:29
 * @LastEditTime: 2021-04-07 20:44:50
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day91.md
-->
### 翻转字符串里的单词
给定一个字符串，逐个翻转字符串中的每个单词。

说明：

无空格字符构成一个 单词 。
输入字符串可以在前面或者后面包含多余的空格，但是反转后的字符不能包括。
如果两个单词间有多余的空格，将反转后单词间的空格减少到只含一个。

链接：https://leetcode-cn.com/leetbook/read/array-and-string/crmp5/

```
var reverseWords = function(s) {
  return s.trim().split(/\s+/).reverse().join(' ');
};
```