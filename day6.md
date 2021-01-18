<!--
 * @Author: 月魂
 * @Date: 2021-01-12 21:00:18
 * @LastEditTime: 2021-01-17 17:48:31
 * @LastEditors: 月魂
 * @Description:
 * @FilePath: \leetcode-per-day\day6.md
-->
### 只出现一次的数字

给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。

链接：https://leetcode-cn.com/problems/single-number/solution/hua-jie-suan-fa-136-zhi-chu-xian-yi-ci-de-shu-zi-b/


```
// 我的解法
var singleNumber = function(nums) {
  nums.sort((a, b) => a - b);
  for (let i = 0; i < nums.length; i += 2) {
    if (nums[i] !== nums[i + 1]) return nums[i];
  }
};

// 位运算
var singleNumber = function(nums) {
  let ans = 0;
  for(const num of nums) {
     ans ^= num;
  }
  return ans;
};

```