## 用两个栈实现队列（Python）
**题目**
用两个栈来实现一个队列，完成队列的Push和Pop操作。 队列中的元素为int类型。
**思路**
栈：先进后出
队列：先进先出

 - 栈1为入队队列
 - 栈2为出队队列。当栈2为空时且栈1不为空时，把栈1中的元素一个个出栈然后压进栈2，最后栈2元素一个个出栈。

 **代码**


```python
class Solution:
    def __init__(self):
        self.stack1 = []
        self.stack2 = []
    def push(self, node):
        # write code here
        self.stack1.append(node)
    def pop(self):
        # return xx
        if self.stack2 == []:
            while self.stack1:
                self.stack2.append(self.stack1.pop())
        return self.stack2.pop()
```