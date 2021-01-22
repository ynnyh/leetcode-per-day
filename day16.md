<!--
 * @Author: 月魂
 * @Date: 2021-01-22 22:28:31
 * @LastEditTime: 2021-01-22 22:28:56
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day16.md
-->

### 验证回文串
给定一个字符串，验证它是否是回文串，只考虑字母和数字字符，可以忽略字母的大小写。

说明：本题中，我们将空字符串定义为有效的回文串。

```
var isPalindrome = function(s) {
  const arr = s.toLowerCase().match(/[A-Za-z0-9]+/g);
  if (!arr) return true;
  const str = arr.join('');
  let p1 = 0;
  let p2 = str.length - 1;
  while(p1 < p2) {
    if (str[p1] === str[p2]) {
      p1++;
      p2--;
    } else {
      return false;
    }
  }
  return true;
};
```
