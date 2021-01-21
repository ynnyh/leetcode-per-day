<!--
 * @Author: 月魂
 * @Date: 2021-01-21 21:26:57
 * @LastEditTime: 2021-01-21 21:29:58
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day15.md
-->

### 有效的字母异位词
给定两个字符串 s 和 t ，编写一个函数来判断 t 是否是 s 的字母异位词。

```
var isAnagram = function(s, t) {
  return s.length === t.length && [...s].sort().join('') === [...t].sort().join('') ? true : false;
};
```