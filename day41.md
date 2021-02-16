<!--
 * @Author: 月魂
 * @Date: 2021-02-16 19:59:11
 * @LastEditTime: 2021-02-16 19:59:44
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day41.md
-->
### 数组拆分 I
给定长度为 2n 的整数数组 nums ，你的任务是将这些数分成 n 对, 例如 (a1, b1), (a2, b2), ..., (an, bn) ，使得从 1 到 n 的 min(ai, bi) 总和最大。

返回该 最大总和 。

链接：https://leetcode-cn.com/problems/array-partition-i

```
var arrayPairSum = function(nums) {
  // 排序
  nums.sort((a, b) => a - b);
  let ans = 0;
  // 将下标为偶数的相加
  for(let i = 0; i < nums.length; i++) {
    if (i % 2 === 0) {
      ans += nums[i];
    }
  }
  return ans;
};
```