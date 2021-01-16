<!--
 * @Author: 月魂
 * @Date: 2021-01-16 19:06:28
 * @LastEditTime: 2021-01-16 21:37:17
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day10.md
-->
### 有效的数独
判断一个 9x9 的数独是否有效。只需要根据以下规则，验证已经填入的数字是否有效即可。

1. 数字 1-9 在每一行只能出现一次。
2. 数字 1-9 在每一列只能出现一次。
3. 数字 1-9 在每一个以粗实线分隔的 3x3 宫内只能出现一次。

链接：https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/x2f9gg/

```
// 我的解法
var isValidSudoku = function(board) {
  // 先判断内部九个数组是否有重复值
  for (let i = 0; i < board.length; i++) {
    let p1 = 0;
    let arr = board[i];
    let s = new Set();
    while (p1 < arr.length) {
      if (s.has(arr[p1]) && arr[p1] !== '.') {
        return false;
      }
      s.add(arr[p1]);
      p1++;
    }
  }
  // 判断每列是否有重复值
  let p1 = 0;
  let p2 = 0;
  let s = new Set();
  while (p1 < board.length) {
    if (s.has(board[p2][p1]) && board[p2][p1] !== '.') {
      return false;
    } else if (p2 === board.length - 1) {
      p1++;
      p2 = 0;
      s.clear()
    } else {
      s.add(board[p2][p1])
      p2++;
    }
  }

  // 判断3*3是否有重复
  let z1 = 0;
  let z2 = 0;
  let s1 = new Set();
  while (z1 < 3) {
    if (z2 === 9) {
      z1++;
      z2 = 0;
      s1.clear();
      continue;
    }
    let arr = board[z2].splice(0, 3);
    if (z2 === 3 || z2 ===6) {
      z2++;
      s1.clear();
    } else {
      z2++;
    }
    for (let i = 0; i < arr.length; i++) {
      if (s1.has(arr[i]) && arr[i] !== '.') {
        return false;
      } else {
        s1.add(arr[i]);
      }
    }
  }
  return true;
};
```
