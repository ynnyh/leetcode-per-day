<!--
 * @Author: 月魂
 * @Date: 2021-03-11 10:22:23
 * @LastEditTime: 2021-03-11 10:23:31
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day64.md
-->
### 有效的括号
给定一个只包括 '('，')'，'{'，'}'，'['，']' 的字符串 s ，判断字符串是否有效。

有效字符串需满足：

左括号必须用相同类型的右括号闭合。
左括号必须以正确的顺序闭合。

链接：https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/xnbcaj/

```
var isValid = function(s) {
  if (s.length === 0) return true;
  if (s.length % 2 !== 0) return false;
  let map = new Map([
    ['(', ")"],
    ["[", "]"],
    ["{", "}"]
  ]);
  let splitArr = s.split('');
  let arr = [];
  for (let i = 0; i < splitArr.length; i++) {
    const target = splitArr[i];
    if (map.has(target)) {
      arr.push(target);
    } else {
      if (map.get(arr[arr.length - 1]) === target) {
        arr.pop();
      } else {
        return false;
      }
    }
  }
  return !arr.length;
};
```