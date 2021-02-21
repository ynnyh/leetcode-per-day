<!--
 * @Author: 月魂
 * @Date: 2021-02-21 19:24:39
 * @LastEditTime: 2021-02-21 19:25:11
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day46.md
-->
### 杨辉三角
给定一个非负整数 numRows，生成杨辉三角的前 numRows 行。

```
var generate = function(numRows) {
  let ans = [];
  for (let i = 0; i < numRows; i++) {
    let row = new Array(i + 1).fill(1);
    for (let j = 1; j < row.length - 1; j++) {
      row[j] = ans[i - 1][j - 1] + ans[i - 1][j];
    }
    ans.push(row);
  }
  return ans;
};
```