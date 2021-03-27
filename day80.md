<!--
 * @Author: 月魂
 * @Date: 2021-03-27 21:08:02
 * @LastEditTime: 2021-03-27 21:08:23
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day80.md
-->
### 分割数组
给定一个数组 A，将其划分为两个连续子数组 left 和 right， 使得：

left 中的每个元素都小于或等于 right 中的每个元素。
left 和 right 都是非空的。
left 的长度要尽可能小。
在完成这样的分组后返回 left 的长度。可以保证存在这样的划分方法。

链接：https://leetcode-cn.com/problems/partition-array-into-disjoint-intervals

```
var partitionDisjoint = function(A) {
  let max = [];
  let min = [];
  let num = A[0];
  let N = A.length;
  for (let i = 0; i < N; i++) {
    num = Math.max(num, A[i]);
    max[i] = num;
  }
  num = A[N - 1];
  for (let i = N - 1; i >= 0; i--) {
    num = Math.min(num, A[i]);
    min[i] = num;
  }
  for (let i = 1; i < N; i++) {
    if (max[i - 1] <= min[i]) {
      return i;
    }
  }
};
```