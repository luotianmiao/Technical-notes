---
title: 链表中倒数第k个结点

date: 2020-3-26 12:59

tags:

- 算法

- 链表

- 指针

-剑指offer

category:

- python
---

## 链表中倒数第k个结点

### 题目

输入一个链表，输出该链表中倒数第k个结点。

### 思路

用两个指针，指针p、q最开始都指向 head，p 先向右移动 k 位，然后 p 和 q 再一起同步向右移动，当 p 到达边界时（p指向空）， q 正好指向了倒数第 k 个结点

做完这些还不能通过牛客网的测试，因为出现了 k 会大于整个链表长度的情况，因此在 p 向右边移动的时候做出判断，如果在移动到 k 位之前 p 就已经到达边界了，那么直接返回空即可

### 代码

```python
class Solution:
    def FindKthToTail(self, head, k):
        # write code here
        p = head
        q = head
        i = 0
        while i < k:
            #如果在移动到 k 位之前 p 就已经到达边界了，那么直接返回空即可
            if p is None:
                return None
            p = p.next
            i += 1
        while p:
            p = p.next
            q = q.next
        return q
```

