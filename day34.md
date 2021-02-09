<!--
 * @Author: 月魂
 * @Date: 2021-02-09 17:18:26
 * @LastEditTime: 2021-02-09 17:19:09
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day34.md
-->
### K 个不同整数的子数组
给定一个正整数数组 A，如果 A 的某个子数组中不同整数的个数恰好为 K，则称 A 的这个连续、不一定独立的子数组为好子数组。

（例如，[1,2,3,1,2] 中有 3 个不同的整数：1，2，以及 3。）

返回 A 中好子数组的数目。

链接：https://leetcode-cn.com/problems/subarrays-with-k-different-integers

```
var subarraysWithKDistinct = function(A, K) {
  return cal(A, K) - cal(A, K - 1);
};

const cal = function(arr, num) {
  let left = 0;
  let right = 0;
  let count = 0;
  let res = 0;
  let s = new Array(arr.length + 1).fill(0);
  while(right < arr.length) {
    if (s[arr[right]] === 0) {
      count++;;
    }
    s[arr[right]]++;
    right++;
    while(count > num) {
      s[arr[left]]--;
      if (s[arr[left]] === 0) {
        count--;
      }
      left++;
    }
    res = res + right - left;
  }
  return res;
}
```