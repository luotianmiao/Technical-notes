---
title: 反转链表

date: 2020-3-26 13:35

tags:

- 算法

- 链表

- 指针

-剑指offer

category:

- python
---

## 反转链表(python)

### 题目

输入一个链表，反转链表后，输出新链表的表头。

### 思路

用到三个指针，目的是改变指针指向

### 代码

```python
class Solution:
    # 返回ListNode
    def ReverseList(self, pHead):
        # write code here
        #指针pre记录当前结点的前一个结点
        pre = None
        #指针pnext记录当前结点的后一个结点
        pnext = None
        while pHead:
            #用指针pnext记录当前结点的后一个结点
            pnext = pHead.next
            #改变当前节点的指针指向，使之指向前一个结点
            pHead.next = pre
            #指针pre指向当前结点
            pre = pHead
            #指针pHead指向pnext（保存着原链表中pHead的下一个结点）
            pHead = pnext
        return pre #最后pre指向的是反转链表的头结点
```

