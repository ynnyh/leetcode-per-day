<!--
 * @Author: 月魂
 * @Date: 2021-03-20 17:46:58
 * @LastEditTime: 2021-03-20 17:47:47
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day73.md
-->
### 无重复字符的最长子串
给定一个字符串，请你找出其中不含有重复字符的 最长子串 的长度。

```
var lengthOfLongestSubstring = function(s) {
  if (s.length <= 1) {
    return s.length;
  }
  let map = new Map();
  let p1 = 0;
  let p2 = 0;
  let ans = 0;
  while (p2 < s.length) {
    if (map.has(s[p2])) {
      ans = Math.max(ans, p2 - p1);
      for (let i = p1; i < map.get(s[p2]); i++) {
        map.delete(s[i]);
      }
      p1 = map.get(s[p2]) + 1;
      map.delete(s[p2]);
    } else {
      map.set(s[p2], p2);
      p2++;
    }
  }
  return Math.max(ans, map.size);
};

// 第二种解法
var lengthOfLongestSubstring = function(s) {
    // 哈希集合，记录每个字符是否出现过
    const occ = new Set();
    const n = s.length;
    // 右指针，初始值为 -1，相当于我们在字符串的左边界的左侧，还没有开始移动
    let rk = -1, ans = 0;
    for (let i = 0; i < n; ++i) {
        if (i != 0) {
            // 左指针向右移动一格，移除一个字符
            occ.delete(s.charAt(i - 1));
        }
        while (rk + 1 < n && !occ.has(s.charAt(rk + 1))) {
            // 不断地移动右指针
            occ.add(s.charAt(rk + 1));
            ++rk;
        }
        // 第 i 到 rk 个字符是一个极长的无重复字符子串
        ans = Math.max(ans, rk - i + 1);
    }
    return ans;
};

```