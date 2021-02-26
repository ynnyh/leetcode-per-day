<!--
 * @Author: 月魂
 * @Date: 2021-02-26 10:49:18
 * @LastEditTime: 2021-02-26 10:49:45
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day51.md
-->
### 合并两个有序数组
给你两个有序整数数组 nums1 和 nums2，请你将 nums2 合并到 nums1 中，使 nums1 成为一个有序数组。

初始化 nums1 和 nums2 的元素数量分别为 m 和 n 。你可以假设 nums1 的空间大小等于 m + n，这样它就有足够的空间保存来自 nums2 的元素。

链接：https://leetcode-cn.com/problems/merge-sorted-array

```
var merge = function(nums1, m, nums2, n) {
  let left = 0;
  let right = 0;
  let ans = [];
  let tmp1 = nums1.slice(0, m);
  let tmp2 = nums2.slice(0, n);
  while (left < m && right < n) {
    if (tmp1[left] <= tmp2[right]) {
      ans.push(tmp1[left]);
      left++;
    } else {
      ans.push(tmp2[right]);
      right++;
    }
  }
  ans = ans.concat(tmp1.slice(left).concat(tmp2.slice(right)));
  for (let i = 0; i < ans.length; i++) {
    nums1[i] = ans[i];
  }
};
```