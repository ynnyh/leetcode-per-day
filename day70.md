<!--
 * @Author: 月魂
 * @Date: 2021-03-17 11:38:25
 * @LastEditTime: 2021-03-17 11:38:44
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day70.md
-->
### 统计匹配检索规则的物品数量
给你一个数组 items ，其中 items[i] = [typei, colori, namei] ，描述第 i 件物品的类型、颜色以及名称。

另给你一条由两个字符串 ruleKey 和 ruleValue 表示的检索规则。

如果第 i 件物品能满足下述条件之一，则认为该物品与给定的检索规则 匹配 ：

ruleKey == "type" 且 ruleValue == typei 。
ruleKey == "color" 且 ruleValue == colori 。
ruleKey == "name" 且 ruleValue == namei 。
统计并返回 匹配检索规则的物品数量 。

链接：https://leetcode-cn.com/problems/count-items-matching-a-rule

```
var countMatches = function(items, ruleKey, ruleValue) {
  let map = {
    type: 0,
    color: 1,
    name: 2,
  };
  let ans = 0;
  items.map(node => {
    if (node[map[ruleKey]] === ruleValue) {
      ans++;
    }
  })
  return ans;
};
```