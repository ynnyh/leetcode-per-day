<!--
 * @Author: 月魂
 * @Date: 2021-03-31 17:11:00
 * @LastEditTime: 2021-03-31 17:11:24
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day84.md
-->
## 合并区间
以数组 intervals 表示若干个区间的集合，其中单个区间为 intervals[i] = [starti, endi] 。请你合并所有重叠的区间，并返回一个不重叠的区间数组，该数组需恰好覆盖输入中的所有区间。

链接：https://leetcode-cn.com/problems/merge-intervals

```
var merge = function(intervals) {
  let ans = [];
  intervals.sort((a, b) => a[0] - b[0]);
  let prev = intervals[0];
  for (let i = 1; i < intervals.length; i++) {
    if (prev[1] >= intervals[i][0]) {
      prev[1] = Math.max(intervals[i][1], prev[1]);
    } else {
      ans.push(prev);
      prev = intervals[i];
    }
  }
  ans.push(prev);
  return ans;
};
```