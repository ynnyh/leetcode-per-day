<!--
 * @Author: 月魂
 * @Date: 2021-04-10 11:27:53
 * @LastEditTime: 2021-04-10 11:28:17
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day94.md
-->
### 杨辉三角 II
给定一个非负索引 k，其中 k ≤ 33，返回杨辉三角的第 k 行。

在杨辉三角中，每个数是它左上方和右上方的数的和。

```
var getRow = function(rowIndex) {
  let ans = [];
  let n = rowIndex;
  for (let i = 0; i <= n; i++) {
    let row = new Array(i + 1).fill(1);
    for (let j = 1; j < row.length - 1; j++) {
      row[j] = ans[i - 1][j - 1] + ans[i - 1][j];
    }
    ans.push(row);
  }
  return ans[rowIndex];
};
```
