<!--
 * @Author: 月魂
 * @Date: 2021-02-06 20:08:21
 * @LastEditTime: 2021-02-06 20:08:46
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day31.md
-->
### 可获得的最大点数
几张卡牌 排成一行，每张卡牌都有一个对应的点数。点数由整数数组 cardPoints 给出。

每次行动，你可以从行的开头或者末尾拿一张卡牌，最终你必须正好拿 k 张卡牌。

你的点数就是你拿到手中的所有卡牌的点数之和。

给你一个整数数组 cardPoints 和整数 k，请你返回可以获得的最大点数。

链接：https://leetcode-cn.com/problems/maximum-points-you-can-obtain-from-cards

```
var maxScore = function(cardPoints, k) {
  let ans = 0;
  if (k >= cardPoints.length) {
    ans = cardPoints.reduce((now, next) => now + next);
    return ans;
  }
  for (let i = 0; i < k; i++) {
    ans += cardPoints[i];
  }
  let maxSum = ans;
  let start = k - 1;
  let end = cardPoints.length - 1;
  while (start >= 0) {
    ans = ans - cardPoints[start] + cardPoints[end];
    maxSum = Math.max(maxSum, ans);
    start--;
    end--;
  }
  return maxSum;
};
```