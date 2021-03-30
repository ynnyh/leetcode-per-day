<!--
 * @Author: 月魂
 * @Date: 2021-03-30 20:40:15
 * @LastEditTime: 2021-03-30 20:40:38
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day83.md
-->
### 寻找数组的中心下标
给你一个整数数组 nums，请编写一个能够返回数组 “中心下标” 的方法。

数组 中心下标 是数组的一个下标，其左侧所有元素相加的和等于右侧所有元素相加的和。

如果数组不存在中心下标，返回 -1 。如果数组有多个中心下标，应该返回最靠近左边的那一个。

注意：中心下标可能出现在数组的两端。

链接：https://leetcode-cn.com/problems/find-pivot-index

```
var pivotIndex = function(nums) {
  let sum = 0;
  const amount = nums.reduce((pre, cur) => pre + cur, 0);
  for (let i = 0; i < nums.length; i++) {
    if (2 * sum + nums[i] === amount) {
      return i;
    } else {
      sum += nums[i];
    }
  }
  return -1;
};
```