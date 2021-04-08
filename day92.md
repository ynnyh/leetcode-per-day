<!--
 * @Author: 月魂
 * @Date: 2021-04-08 11:11:41
 * @LastEditTime: 2021-04-08 11:12:01
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day92.md
-->
### 两数之和 II - 输入有序数组
给定一个已按照 升序排列  的整数数组 numbers ，请你从数组中找出两个数满足相加之和等于目标数 target 。

函数应该以长度为 2 的整数数组的形式返回这两个数的下标值。numbers 的下标 从 1 开始计数 ，所以答案数组应当满足 1 <= answer[0] < answer[1] <= numbers.length 。

你可以假设每个输入只对应唯一的答案，而且你不可以重复使用相同的元素。

链接：https://leetcode-cn.com/leetbook/read/array-and-string/cnkjg/

```
var twoSum = function(numbers, target) {
  let p1 = 0;
  p2 = numbers.length - 1;
  while (p1 < p2) {
    if (numbers[p1] + numbers[p2] < target) p1++;
    if (numbers[p1] + numbers[p2] > target) p2--;
    if (numbers[p1] + numbers[p2] === target) return [p1 + 1, p2 + 1];
  }
};
```