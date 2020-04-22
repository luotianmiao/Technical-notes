---
title: 调整数组顺序使奇数位于偶数前面

date: 2020-3-26 12:46

tags:

- 算法

- 数组

-剑指offer

category:

- python
---

## 调整数组顺序使奇数位于偶数前面(python)

### 题目

输入一个整数数组，实现一个函数来调整该数组中数字的顺序，使得所有的奇数位于数组的前半部分，所有的偶数位于数组的后半部分，并保证奇数和奇数，偶数和偶数之间的相对位置不变。

### 思路1

遍历数组，遇到奇数忽略，遇到偶数后，首先将该偶数加到数组末尾，再删掉该偶数

### 代码

```python
class Solution:
    def reOrderArray(self, array):
        # write code here
        i = 0
        lenA = len(array)
        while i < lenA:
            if array[i] % 2 == 0:
                array.append(array[i])
                del(array[i])
                lenA -= 1 #删除array[i]后，后面的数字往前移，所以下一次操作的数组下标仍然是i，但
                #是要通过lenA -= 1 减少一次遍历次数
            else:
                i += 1
        return array
```



### 思路2

创建两个空数组，遍历原数组，奇数偶数分别放入两个数组，然后拼接起来

### 代码

```python
class Solution:
    def reOrderArray(self, array):
        # write code here
        arr1 = []
        arr2 = []
        for i in array:
            if i % 2 == 0:
                arr2.append(i)
            else:
                arr1.append(i)
        return arr1 + arr2
```

