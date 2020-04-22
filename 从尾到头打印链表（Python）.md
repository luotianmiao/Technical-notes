## 从尾到头打印链表（Python）
**题目**
输入一个链表，按链表从尾到头的顺序返回一个ArrayList。

**思路1**
创建一个列表，把链表里的元素从头到尾依次放入列表中，然后反转列表
```python
class Solution:
    # 返回从尾部到头部的列表值序列，例如[1,2,3]
    def printListFromTailToHead(self, listNode):
        # write code here
        Arraylist = []
        while listNode:
            Arraylist.append(listNode.val)
            listNode = listNode.next
        Arraylist.reverse()
        return Arraylist
```
**思路2（递归）**

```python
class Solution:
    # 返回从尾部到头部的列表值序列，例如[1,2,3]
    def __init__(self):
        self.Arraylist = []
    def printListFromTailToHead(self, listNode):
        # write code here
        if listNode :
            self.printListFromTailToHead(listNode.next)#会递归到最后一个值
            self.Arraylist.append(listNode.val)
        return self.Arraylist
```