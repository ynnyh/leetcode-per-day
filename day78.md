<!--
 * @Author: 月魂
 * @Date: 2021-03-25 21:16:11
 * @LastEditTime: 2021-03-25 21:23:41
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day78.md
-->
### 删除排序链表中的重复元素

给定一个排序链表，删除所有重复的元素，使得每个元素只出现一次。

```
var deleteDuplicates = function(head) {
  let p = head;
  while(p && p.next) {
    if (p.val === p.next.val) {
      p.next = p.next.next;
    } else {
      p = p.next;
    }
  }
  return head;
};
```