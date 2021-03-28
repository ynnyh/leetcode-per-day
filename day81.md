<!--
 * @Author: 月魂
 * @Date: 2021-03-28 12:40:57
 * @LastEditTime: 2021-03-28 12:41:16
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day81.md
-->
### 二叉树的深度
输入一棵二叉树的根节点，求该树的深度。从根节点到叶节点依次经过的节点（含根、叶节点）形成树的一条路径，最长路径的长度为树的深度。

```
var maxDepth = function(root) {
  if (!root) {
    return 0;
  }
  return Math.max(maxDepth(root.left), maxDepth(root.right)) + 1;
};
```
