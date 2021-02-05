<!--
 * @Author: 月魂
 * @Date: 2021-02-05 15:43:38
 * @LastEditTime: 2021-02-05 15:44:38
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day30.md
-->

### 尽可能使字符串相等
给你两个长度相同的字符串，s 和 t。

将 s 中的第 i 个字符变到 t 中的第 i 个字符需要 |s[i] - t[i]| 的开销（开销可能为 0），也就是两个字符的 ASCII 码值的差的绝对值。

用于变更字符串的最大预算是 maxCost。在转化字符串时，总开销应当小于等于该预算，这也意味着字符串的转化可能是不完全的。

如果你可以将 s 的子字符串转化为它在 t 中对应的子字符串，则返回可以转化的最大长度。

如果 s 中没有子字符串可以转化成 t 中对应的子字符串，则返回 0。

链接：https://leetcode-cn.com/problems/get-equal-substrings-within-budget

```
var equalSubstring = function(s, t, maxCost) {
  let diff = new Array(s.length).fill(0);
  for (let i = 0; i < diff.length; i++) {
    diff[i] = Math.abs(s[i].charCodeAt() - t[i].charCodeAt());
  }
  let maxLength = 0;
  let start = 0;
  let end = 0;
  let sum = 0;
  while(end < s.length) {
    sum += diff[end];
    while(sum > maxCost) {
      sum -= diff[start];
      start++;
    }
    maxLength = Math.max(maxLength, end - start + 1);
    end++;
  }
  return maxLength;
};
```