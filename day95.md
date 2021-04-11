<!--
 * @Author: 月魂
 * @Date: 2021-04-11 11:17:00
 * @LastEditTime: 2021-04-11 11:17:22
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day95.md
-->
### 反转字符串中的单词 III
给定一个字符串，你需要反转字符串中每个单词的字符顺序，同时仍保留空格和单词的初始顺序。

```
var reverseWords = function(s) {
  let arr = s.split(' ');
  let ans = [];
  for (let i = 0; i < arr.length; i++) {
    let str = arr[i].split('').reverse().join('');
    ans.push(str);
  }
  return ans.join(' ');
};
```
