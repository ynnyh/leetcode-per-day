<!--
 * @Author: 月魂
 * @Date: 2021-03-14 12:42:21
 * @LastEditTime: 2021-03-14 12:42:53
 * @LastEditors: 月魂
 * @Description: 
 * @FilePath: \leetcode-per-day\day67.md
-->
### 设计哈希映射
不使用任何内建的哈希表库设计一个哈希映射（HashMap）。

实现 MyHashMap 类：

MyHashMap() 用空映射初始化对象
void put(int key, int value) 向 HashMap 插入一个键值对 (key, value) 。如果 key 已经存在于映射中，则更新其对应的值 value 。
int get(int key) 返回特定的 key 所映射的 value ；如果映射中不包含 key 的映射，返回 -1 。
void remove(key) 如果映射中存在 key 的映射，则移除 key 和它所对应的 value 。

链接：https://leetcode-cn.com/problems/design-hashmap

```
var MyHashMap = function() {
  this.BASE = 769;
  this.data = new Array(this.BASE).fill(0).map(() => new Array());
};

/**
 * value will always be non-negative. 
 * @param {number} key 
 * @param {number} value
 * @return {void}
 */
MyHashMap.prototype.put = function(key, value) {
  const h = this.hash(key);
  for (const i of this.data[h]) {
    if (i[0] === key) {
      i[1] = value;
      return;
    }
  }
  this.data[h].push([key, value]);
};

/**
 * Returns the value to which the specified key is mapped, or -1 if this map contains no mapping for the key 
 * @param {number} key
 * @return {number}
 */
MyHashMap.prototype.get = function(key) {
  const h = this.hash(key);
  for (const i of this.data[h]) {
    if (i[0] === key) {
      return i[1];
    }
  }
  return -1;
};

/**
 * Removes the mapping of the specified value key if this map contains a mapping for the key 
 * @param {number} key
 * @return {void}
 */
MyHashMap.prototype.remove = function(key) {
  const h = this.hash(key);
  for (const i of this.data[h]) {
    if (i[0] === key) {
      const idx = this.data[h].indexOf(i);
      this.data[h].splice(idx, 1);
      return;
    }
  }
};

MyHashMap.prototype.hash = function(key) {
  return key % this.BASE;
}

```