## 替换空格（python）
**题目**
请实现一个函数，将一个字符串中的每个空格替换成“%20”。例如，当字符串为We Are Happy.则经过替换之后的字符串为We%20Are%20Happy。

**思路1（创建新字符串）**

 创建一个新字符串ss， 遍历原字符串，如果遇到空格则将‘%20’加入新字符串，否则将遍历到的非空字符加入新字符串ss

```python
class Solution:
    # s 源字符串
    def replaceSpace(self, s):
        ss = ''
        for i in s:
            if i == ' ':
                ss += '%20'
            else:
                ss += i
        return ss
```
**思路2**
用内置函数replace将空格替换为‘%20’

```python
class Solution:
    # s 源字符串
    def replaceSpace(self, s):
        # write code here
        return s.replace(' ','%20')
```