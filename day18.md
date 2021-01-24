<!--
 * @Author: 月魂
 * @Date: 2021-01-24 16:12:44
 * @LastEditTime: 2021-01-24 16:13:22
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day18.md
-->

### 实现 strStr()

给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。

链接：https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/xnr003/

```
var strStr = function(haystack, needle) {
  let p1 = 0;
  let p2 = needle.length;
  if (needle === '') return 0;
  while(p1 < haystack.length) {
    let str = haystack.slice(p1, p2);
    if (str === needle) {
      return p1;
    } else {
      p1++;
      p2++;
    }
  }
  return -1;
};
```