<!--
 * @Author: 月魂
 * @Date: 2021-02-12 17:32:42
 * @LastEditTime: 2021-02-12 17:33:17
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day37.md
-->
### 回文数
给你一个整数 x ，如果 x 是一个回文整数，返回 true ；否则，返回 false 。

回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。例如，121 是回文，而 123 不是。

链接：https://leetcode-cn.com/problems/palindrome-number

```
var isPalindrome = function(x) {
  x += '';
  let left = 0;
  let right = x.length - 1;
  while (left < right) {
    if (x[left] === x[right]) {
      left++;
      right--;
    } else {
      return false;
    }
  }
  return true;
};
```