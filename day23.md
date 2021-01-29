<!--
 * @Author: 月魂
 * @Date: 2021-01-29 22:54:36
 * @LastEditTime: 2021-01-29 22:55:10
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day23.md
-->

### 盛最多水的容器
给你 n 个非负整数 a1，a2，...，an，每个数代表坐标中的一个点 (i, ai) 。在坐标内画 n 条垂直线，垂直线 i 的两个端点分别为 (i, ai) 和 (i, 0) 。找出其中的两条线，使得它们与 x 轴共同构成的容器可以容纳最多的水。

说明：你不能倾斜容器。

链接：https://leetcode-cn.com/problems/container-with-most-water

```
var maxArea = function(height) {
  let p1 = 0;
  let p2 = height.length - 1;
  let ans = 0;
  while(p1 < p2) {
    let min = Math.min(height[p1], height[p2]);
    let num = (p2 - p1) * min;
    if (ans < num) {
      ans = num;
    }
    if (height[p1] <= height[p2]) {
      p1++;
    } else {
      p2--;
    }
  }
  return ans;
};
```