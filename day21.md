<!--
 * @Author: 月魂
 * @Date: 2021-01-27 19:50:56
 * @LastEditTime: 2021-01-27 19:51:23
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day21.md
-->

### 删除链表中的节点
请编写一个函数，使其可以删除某个链表中给定的（非末尾）节点。传入函数的唯一参数为 要被删除的节点 

```
var deleteNode = function(node) {
  node.val = node.next.val;
  node.next = node.next.next;
};
```
