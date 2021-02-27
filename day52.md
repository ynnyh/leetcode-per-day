<!--
 * @Author: 月魂
 * @Date: 2021-02-27 18:04:03
 * @LastEditTime: 2021-02-27 18:04:55
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day52.md
-->
### 第一个错误的版本
你是产品经理，目前正在带领一个团队开发新的产品。不幸的是，你的产品的最新版本没有通过质量检测。由于每个版本都是基于之前的版本开发的，所以错误的版本之后的所有版本都是错的。

假设你有 n 个版本 [1, 2, ..., n]，你想找出导致之后所有版本出错的第一个错误的版本。

你可以通过调用 bool isBadVersion(version) 接口来判断版本号 version 是否在单元测试中出错。实现一个函数来查找第一个错误的版本。你应该尽量减少对调用 API 的次数。

链接：https://leetcode-cn.com/problems/first-bad-version

```
var solution = function(isBadVersion) {
    /**
     * @param {integer} n Total versions
     * @return {integer} The first bad version
     */
    return function(n) {
      let l = 0;
      let r = n;
      while(l < r) {
        let mid = Math.floor((r - l) / 2) + l;
        if (isBadVersion(mid)) {
          r = mid;
        } else {
          l = mid + 1;
        }
      }
      return r;
    };
};
```