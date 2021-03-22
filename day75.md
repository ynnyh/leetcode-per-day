<!--
 * @Author: 月魂
 * @Date: 2021-03-22 13:22:57
 * @LastEditTime: 2021-03-22 13:23:15
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day75.md
-->
### 删除中间节点
实现一种算法，删除单向链表中间的某个节点（即不是第一个或最后一个节点），假定你只能访问该节点。

```
var deleteNode = function(node) {
  node.val = node.next.val;
  node.next = node.next.next;
};
```
