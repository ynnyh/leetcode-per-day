<!--
 * @Author: 月魂
 * @Date: 2021-01-13 21:34:09
 * @LastEditTime: 2021-01-17 17:48:44
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day7.md
-->
### 两个数组的交集 II

链接：https://leetcode-cn.com/leetbook/read/top-interview-questions-easy/x2y0c2/

给定两个数组，编写一个函数来计算它们的交集。

说明：

输出结果中每个元素出现的次数，应与元素在两个数组中出现次数的最小值一致。
我们可以不考虑输出结果的顺序。

```
// 我的解法
var intersect = function(nums1, nums2) {
  let s = [];
  let minArr = nums1.length > nums2.length ? nums2 : nums1;
  let maxArr = nums1.length > nums2.length ? nums1 : nums2;
  for (let i = 0; i < minArr.length; i++) {
    const index = maxArr.findIndex(item => item === minArr[i]);
    if (index !== -1) {
      s.push(minArr[i]);
      maxArr.splice(index, 1);
    }
  }
  return s;
};

// 解法1
var intersect = function(nums1, nums2) {
  let obj = {};
  let arr = [];
  for (let i = 0; i < nums1.length; i++) {
    if (obj[nums1[i]]) {
      obj[nums1[i]]++;
    } else {
      obj[nums1[i]] = 1;
    }
  }
  for(let i = 0; i < nums2.length; i++) {
    if (obj[nums2[i]] > 0) {
      arr.push(nums2[i]);
      obj[nums2[i]]--;
    }
  }
  return arr;
};

// 解法2
var intersect = function(nums1, nums2) {
  nums1.sort((a, b) => a - b);
  nums2.sort((a, b) => a - b);
  let p1 = 0;
  let p2 = 0;
  let arr = [];
  while(p1 < nums1.length && p2 < nums2.length) {
    if (nums1[p1] > nums2[p2]) {
      p2++;
    } else if (nums1[p1] < nums2[p2]) {
      p1++;
    } else {
      arr.push(nums1[p1]);
      p1++;
      p2++;
    }
  }
  return arr;
};

```