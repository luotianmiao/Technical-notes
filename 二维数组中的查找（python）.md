## 二维数组中的查找（python）
**题目描述**
在一个二维数组中（每个一维数组的长度相同），每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。

**思路（右上角开始）**
该二维数组特性是数字大小每一行从左到右递增，每一列从上到下递增。
因此可以从右上角开始遍历：

 1. 该数字大于目标数字target，则该行前面可能有目标数字target，继续向前遍历，列标 -1
 2. 该数字小于目标数字target，则该行前面不可能有目标数字target，转向下一行，行标 +1
 3. 该数字等于目标数字，返回True
![演示实例](https://img-blog.csdnimg.cn/20200305134354186.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80Mzg5MzY3OQ==,size_16,color_FFFFFF,t_70)

**代码示例（Python）**

```python
# -*- coding:utf-8 -*-
class Solution:
    # array 二维列表
    def Find(self, target, array):
        # write code here
        rows = len(array)#总行数
        columns = len(array[0])#总列数
        row = 0
        column = columns - 1
        while row < rows and column >= 0:
            if array[row][column] == target:
                return True
            elif array[row][column] < target:
                row += 1
            else:
                column -= 1
        return False
```