<!--
 * @Author: 月魂
 * @Date: 2021-04-05 19:55:06
 * @LastEditTime: 2021-04-05 19:55:35
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day89.md
-->
### 最后一个单词的长度
给你一个字符串 s，由若干单词组成，单词之间用空格隔开。返回字符串中最后一个单词的长度。如果不存在最后一个单词，请返回 0 。

单词 是指仅由字母组成、不包含任何空格字符的最大子字符串。

链接：https://leetcode-cn.com/problems/length-of-last-word

```
var lengthOfLastWord = function(s) {
  let arr = s.trim().split(' ');
  return arr[arr.length - 1].length;
};
```