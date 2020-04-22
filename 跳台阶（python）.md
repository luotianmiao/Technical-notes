---

title: 跳台阶

date: 2020-3-17 13:02

tages:

- 算法

- 迭代

category:

- python

---

## 跳台阶（python）

### 题目

一只青蛙一次可以跳上1级台阶，也可以跳上2级。求该青蛙跳上一个n级的台阶总共有多少种跳法（先后次序不同算不同的结果）。

### 思路

本质上是斐波那契数列。

记跳n级台阶的跳法有 f(n) 种，

如果最后一次跳了两级，那么一共的跳法是 n-2 级台阶的跳法，即 f(n-2)，

如果最后一次跳了一级，那么一共的跳法是 n-1 级台阶的跳法，即 f(n-1)，

那么 n 级台阶的跳法就有 f(n) = f(n-2) + f(n-1)

我们知道，跳第 0， 1， 2 级台阶的跳法分别为 0，1，2，那么运用迭代的思路，就不难求出 n 级台阶的跳法了。

### 代码

```python
class Solution:
    def jumpFloor(self, number):
        # write code here
        result = [0,1,2]
        for i in range(3,number+1):
            result.append(result[i-2] + result[i-1])
        return result[number]
```

