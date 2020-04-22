---

title: 二进制中1的个数

date: 2020-3-26 11:35

tags:

- 算法

- 位运算

-剑指offer

category:

- python

---

## 二进制中1的个数（python）

### 题目

输入一个整数，输出该数二进制表示中1的个数。其中负数用补码表示。

### 思路

在python中负数不是以补码存储的，所以用 n & 0xffffffff 把该数字转化成补码形式，参考查看 【[Python 对于负数的存储方式和 c++/c/java 不一样](https://www.runoob.com/w3cnote/python-negative-storage.html)】

关于二进制中 1 的个数的求法，有一个小技巧：

- 一个非 0 的数字至少有一位为1
- 该数字减去 1 之后得到的数字为：最右边的 1 以及这个 1 右边的位全部取反

比如 1100 这个数减去 1 之后为：1011

- 将这两个数字进行与操作得到的数字正好消去了最右边那个 1

如 1100 & 1011 = 1000

- 如此循环，直到消除所有的1，在这个过程中，我们只需要记录下该“与操作”的次数即为该二进制中1的个位数

### 代码

```python
class Solution:
    def NumberOf1(self, n):
        # write code here
        count = 0
        if n < 0:
            n = n & 0xffffffff
        while n != 0:
            n &= (n-1)
            count += 1
        return count
```







