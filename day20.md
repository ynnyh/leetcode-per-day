<!--
 * @Author: 月魂
 * @Date: 2021-01-26 20:15:00
 * @LastEditTime: 2021-01-26 20:15:27
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day20.md
-->

### 最长公共前缀

编写一个函数来查找字符串数组中的最长公共前缀。

如果不存在公共前缀，返回空字符串 ""。

```
var longestCommonPrefix = function(strs) {
  if (strs.length === 0) return '';
  let temp = strs[0];
  let p1 = 0;
  let p2 = 0;
  let str = '';
  while (p1 < temp.length) {
    if (p2 === strs.length) {
      str += temp[p1];
      p2 = 0;
      p1++;
    }
    if (temp[p1] === strs[p2][p1]) {
      p2++;
    } else {
      return str;
    }
  }
  return str;
};
```
