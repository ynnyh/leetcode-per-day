<!--
 * @Author: 月魂
 * @Date: 2021-02-01 21:14:06
 * @LastEditTime: 2021-02-01 21:14:41
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day26.md
-->
### 公平的糖果棒交换
爱丽丝和鲍勃有不同大小的糖果棒：A[i] 是爱丽丝拥有的第 i 根糖果棒的大小，B[j] 是鲍勃拥有的第 j 根糖果棒的大小。

因为他们是朋友，所以他们想交换一根糖果棒，这样交换后，他们都有相同的糖果总量。（一个人拥有的糖果总量是他们拥有的糖果棒大小的总和。）

返回一个整数数组 ans，其中 ans[0] 是爱丽丝必须交换的糖果棒的大小，ans[1] 是 Bob 必须交换的糖果棒的大小。

如果有多个答案，你可以返回其中任何一个。保证答案存在。

链接：https://leetcode-cn.com/problems/fair-candy-swap

```
var fairCandySwap = function(A, B) {
  let num1 = A.reduce((a, b) => a + b);
  let num2 = B.reduce((a, b) => a + b);
  let res = (num1 + num2) / 2;
  let p1 = 0;
  let p2 = 0;
  let ans = [];
  while(p1 < A.length) {
    if (num1 - A[p1] + B[p2] === num2 - B[p2] + A[p1]) {
      ans.push(A[p1], B[p2]);
      break;
    } else {
      p2++;
    }
    if (p2 === B.length) {
      p1++;
      p2 = 0;
    }
  }
  return ans;
};
```