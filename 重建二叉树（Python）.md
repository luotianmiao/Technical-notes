## 重建二叉树（Python）
**题目**
输入某二叉树的前序遍历和中序遍历的结果，请重建出该二叉树。假设输入的前序遍历和中序遍历的结果中都不含重复的数字。例如输入前序遍历序列{1,2,4,7,3,5,6,8}和中序遍历序列{4,7,2,1,5,3,8,6}，则重建二叉树并返回。

**思路（递归）**
遍历顺序的命名取决于根节点所在位置：
前序遍历：根结点 ---> 左子树 ---> 右子树
中序遍历：左子树---> 根结点 ---> 右子树
后序遍历：左子树 ---> 右子树 ---> 根结点

 1. 前序遍历的第一个节点是根节点
 2. 找到根节点在中序遍历中的位置index，index左边的是根节点的左子树，右边是根节点的右子树
 3. 再分别进入左右子树，一次次重复上述过程，整个过程是递归的

**代码**

```python
class Solution:
    # 返回构造的TreeNode根节点
    def reConstructBinaryTree(self, pre, tin):
        # write code here
        if len(pre) == 0:
            return None
        elif len(pre) == 1:
            return TreeNode(pre[0])
        else:
            root = TreeNode(pre[0])
            index = tin.index(pre[0])
            root.left = self.reConstructBinaryTree(pre[1 : index+1],tin[0 : index])
            root.right = self.reConstructBinaryTree(pre[index+1 :],tin[index+1 :])
        return root 
```