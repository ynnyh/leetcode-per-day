<!--
 * @Author: 月魂
 * @Date: 2021-01-28 22:00:46
 * @LastEditTime: 2021-01-28 22:01:21
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day22.md
-->

### 寻找两个正序数组的中位数

给定两个大小为 m 和 n 的正序（从小到大）数组 nums1 和 nums2。请你找出并返回这两个正序数组的中位数。

进阶：你能设计一个时间复杂度为 O(log (m+n)) 的算法解决此问题吗？

链接：https://leetcode-cn.com/problems/median-of-two-sorted-arrays

```
// 我的解法
var findMedianSortedArrays = function(nums1, nums2) {
  const length = nums1.length + nums2.length
  if (length === 0) return 0
  if (length === 1) return nums1.length === 0 ? nums2[0] : nums1[0]
  let m = 0
  let n = 0
  let mm = 0
  let nn = 0
  let p = 0
  let p1 = 0
  let p2 = 0
  if (length % 2 === 0) {
    m = length / 2
    n = m + 1
  } else {
    m = Math.ceil(length / 2)
  }
  while (p < Math.max(m, n)) {
    if (p === m - 1) {
      if (!isNaN(Number(nums1[p1])) && nums2[p2]) {
        mm = nums1[p1] <= nums2[p2] ? nums1[p1] : nums2[p2]
      } else {
        mm = nums1[p1] ? nums1[p1] : nums2[p2]
      }
    }
    if (n !== 0 && p === n - 1) {
      if (nums1[p1] && !isNaN(Number(nums2[p2]))) {
        nn = nums1[p1] <= nums2[p2] ? nums1[p1] : nums2[p2]
      } else {
        nn = nums1[p1] ? nums1[p1] : nums2[p2]
      }
    }
    if (!isNaN(Number(nums1[p1])) && !isNaN(Number(nums2[p2]))) {
       if (nums1[p1] <= nums2[p2]) {
        p++
        p1++
      } else {
        p++
        p2++
      }
    } else {
      if (!isNaN(Number(nums1[p1]))) {
        p1++;
        p++;
      } else {
        p2++;
        p++;
      }
    }
   
  }
  if (n === 0) {
    return mm
  }
  return (mm + nn) / 2
};
```