<!--
 * @Author: 月魂
 * @Date: 2021-02-20 10:27:16
 * @LastEditTime: 2021-02-20 10:27:47
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day45.md
-->
### 数组的度
给定一个非空且只包含非负数的整数数组 nums，数组的度的定义是指数组里任一元素出现频数的最大值。

你的任务是在 nums 中找到与 nums 拥有相同大小的度的最短连续子数组，返回其长度。

链接：https://leetcode-cn.com/problems/degree-of-an-array

```
var findShortestSubArray = function(nums) {
  let s = {};
  let count = 0;
  let minLength = 0;
  for (let i = 0; i < nums.length; i++) {
    if (!s[nums[i]]) {
      s[nums[i]] = [1, i, i];
    } else {
      s[nums[i]][0]++;
      s[nums[i]][2] = i;
      if (s[nums[i]][0] > count) {
        count = s[nums[i]][0];
        minLength = s[nums[i]][2] - s[nums[i]][1];
      } else if (s[nums[i]][0] === count) {
        minLength = Math.min(minLength, s[nums[i]][2] - s[nums[i]][1]);
      }
    }
  }
  return minLength + 1;
};
```