<!--
 * @Author: 月魂
 * @Date: 2021-01-20 21:16:24
 * @LastEditTime: 2021-01-20 21:47:14
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day14.md
-->

### 字符串中的第一个唯一字符

给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。

```
var firstUniqChar = function(s) {
  let p = new Map();
  let arr = [];
  for (let [i, v] of Array.from(s).entries()) {
    if (!p.has(v)) {
      p.set(v, i);
      arr.push([s[i], i]);
    } else {
      p.set(v, -1);
      while (arr.length && p.get(arr[0][0]) === -1) {
        arr.shift();
      }
    }
  }
  return arr.length ? arr[0][1] : -1;
};
```
