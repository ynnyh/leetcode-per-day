<!--
 * @Author: 月魂
 * @Date: 2021-02-10 20:22:01
 * @LastEditTime: 2021-02-10 20:22:43
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day35.md
-->
### 字符串的排列
给定两个字符串 s1 和 s2，写一个函数来判断 s2 是否包含 s1 的排列。

换句话说，第一个字符串的排列之一是第二个字符串的子串。

```
var checkInclusion = function(s1, s2) {
  let length = s1.length;
  let count1 = new Array(26).fill(0);
  let count2 = new Array(26).fill(0);
  for (let i = 0; i < length; i++) {
    count1[s1[i].charCodeAt() - 'a'.charCodeAt()]++;
  }
  let left = 0;
  let right = 0;
  while(right < s2.length) {
    count2[s2[right].charCodeAt() - 'a'.charCodeAt()]++;
    while(left <= right && count1[s2[left].charCodeAt() - 'a'.charCodeAt()] < count2[s2[left].charCodeAt() - 'a'.charCodeAt()]) {
      count2[s2[left].charCodeAt() - 'a'.charCodeAt()]--;
      left++;
    }
    if (count1.join('') === count2.join('')) return true;
    right++;
  }
  return false;
};
```
