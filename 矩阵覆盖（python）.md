---

title: 矩阵覆盖

date: 2020-3-25 12:50

tags:

- 剑指offer

- 算法

- 迭代

category:

- python

---

## 矩阵覆盖(python)

### 题目

我们可以用2*1的小矩形横着或者竖着去覆盖更大的矩形。请问用n个2*1的小矩形无重叠地覆盖一个2*n的大矩形，总共有多少种方法？

比如n=3时，2*3的矩形块有3种覆盖方法：

![img](https://uploadfiles.nowcoder.com/images/20200218/6384065_1581999858239_64E40A35BE277D7E7C87D4DCF588BE84)

### 思路

本质上是斐波那契数列，和跳台阶那题方法一样 [跳台阶](http://www.wufeng.online:5001/2020/03/17/%E8%B7%B3%E5%8F%B0%E9%98%B6%EF%BC%88python%EF%BC%89/)

### 代码

```python
class Solution:
    def rectCover(self, number):
        # write code here
        ss = [0,1,2]
        for i in range(3,number+1):
            ss.append(ss[i-1] + ss[i-2])
        return ss[number]
```

