<!--
 * @Author: 月魂
 * @Date: 2021-02-13 19:30:02
 * @LastEditTime: 2021-02-13 19:30:38
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day38.md
-->
### 找到所有数组中消失的数字
给定一个范围在  1 ≤ a[i] ≤ n ( n = 数组大小 ) 的 整型数组，数组中的元素一些出现了两次，另一些只出现一次。

找到所有在 [1, n] 范围之间没有出现在数组中的数字。

您能在不使用额外空间且时间复杂度为O(n)的情况下完成这个任务吗? 你可以假定返回的数组不算在额外空间内。

链接：https://leetcode-cn.com/problems/find-all-numbers-disappeared-in-an-array

```
var findDisappearedNumbers = function(nums) {
  let ans = [];
  let p = 0;
  while(p < nums.length) {
    if (nums[p] == p + 1) {
      p++;
      continue;
    }
    const now = nums[p] - 1;
    if (nums[p] === nums[now]) {
      p++;
      continue;
    }
    [nums[now], nums[p]] = [nums[p], nums[now]];
  }
  for (let i = 0; i < nums.length; i++) {
    if (nums[i] !== i + 1) {
      ans.push(i + 1);
    }
  }
  return ans;
};
```