## 旋转数组的最小数字(python)

**题目**
把一个数组最开始的若干个元素搬到数组的末尾，我们称之为数组的旋转。
输入一个非递减排序的数组的一个旋转，输出旋转数组的最小元素。
例如数组{3,4,5,1,2}为{1,2,3,4,5}的一个旋转，该数组的最小值为1。
NOTE：给出的所有元素都大于0，若数组大小为0，请返回0。
**思路（二分法）**
left = 0
right = len(L) - 1
mid = (left + right) // 2
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200312163114350.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80Mzg5MzY3OQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200312163137303.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80Mzg5MzY3OQ==,size_16,color_FFFFFF,t_70)



**代码**

```python
class Solution:
    def minNumberInRotateArray(self, rotateArray):
        # write code here
        left = 0
        right = len(rotateArray) - 1
        while left < right:
            mid = (left + right) // 2
            if rotateArray[left] < rotateArray[right]:
                return rotateArray[left]
            if rotateArray[mid] > rotateArray[left]:
                left = mid + 1
            elif rotateArray[mid] < rotateArray[left]:
                right = mid
            else:
                left+=1
        return rotateArray[left]
```