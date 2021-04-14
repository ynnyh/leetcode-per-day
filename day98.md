<!--
 * @Author: 月魂
 * @Date: 2021-04-14 22:27:06
 * @LastEditTime: 2021-04-14 22:27:52
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day98.md
-->
### 移除链表元素
给你一个链表的头节点 head 和一个整数 val ，请你删除链表中所有满足 Node.val == val 的节点，并返回 新的头节点 。

```
var removeElements = function(head, val) {
  let res = new ListNode();
  res.next = head;
  let now = res; // 利用引用类型对res进行修改
  while (now.next) {
    if (now.next.val === val) {
      now.next = now.next.next;
    } else {
      now = now.next;
    }
  }
  return res.next;
};
```
