<!--
 * @Author: 月魂
 * @Date: 2021-03-13 23:33:31
 * @LastEditTime: 2021-03-13 23:37:12
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day66.md
-->
### 删除链表的倒数第 N 个结点
给你一个链表，删除链表的倒数第 n 个结点，并且返回链表的头结点。

进阶：你能尝试使用一趟扫描实现吗？

```
var removeNthFromEnd = function(head, n) {
  let preHead = new ListNode(0);
  preHead.next = head;
  let fast = preHead, slow = preHead;
  // 快先走 n+1 步
  while(n--) {
    fast = fast.next;
  }
  // fast、slow 一起前进
  while(fast && fast.next) {
    fast = fast.next;
    slow = slow.next;
  }
  slow.next = slow.next.next;
  return preHead.next;
};
```