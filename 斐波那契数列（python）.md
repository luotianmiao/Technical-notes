---

title: 斐波那契数列

date: 2020-3-15 12:58

tages:

- 算法

- 算法

category:

- python

---

# 斐波那契数列（python）

## 题目

大家都知道斐波那契数列，现在要求输入一个整数n，请你输出斐波那契数列的第n项（从0开始，第0项为0）。

n<=39

## 什么是斐波那契数列？

指的是这样一个数列：1、1、2、3、5、8、13、21、34、……

在数学上定义为：F(1)=1, F(2)=1, F(3)=2, F(4)=3	……	F(n) = F(n - 1) + F(n - 2)

## 思路 1（递归）

###### 时间复杂度o（2^n)，未能在牛客网通过测试：

```python
 class Solution:
 	def Fibonacci(self, n):
        if n == 0:
            return 0
        if n == 1:
            return 1
        return self.Fibonacci(n-2) + self.Fibonacci(n-1)
```

## 思路 2 （迭代）

```python
class Solution:
    def Fibonacci(self, n):
        ss = [0,1,1]
        while len(ss) <= n:
            ss.append(ss[-1] + ss[-2])
        return ss[n]
```



