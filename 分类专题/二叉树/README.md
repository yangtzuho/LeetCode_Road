# 二叉树刷题 
## ACM模式构造二叉树
### 根据数组构造二叉树
**这个函数返回的是根节点的指针**
```c++
//根据数组构造二叉树
TreeNode* construct_binary_tree(const vector<int>& vec)
{
	vector<TreeNode*> vecTree(vec.size(), NULL);
	TreeNode* root = NULL;

	//把输入数值数组，先转化为二叉树节点数组
	for (int i = 0; i < vec.size(); i++)
	{
		TreeNode* node = NULL;
		if (vec[i] != -1) node = new TreeNode(vec[i]);
		vecTree[i] = node;
		if (i == 0) root = node;
	}

	//遍历一遍， 根据规则左右孩子赋值
	for (int i = 0; i * 2 + 2 < vec.size(); i++)
	{
		if (vecTree[i] != NULL)
		{
			//线性存储转链式存储关键逻辑
			vecTree[i]->left = vecTree[i * 2 + 1];
			vecTree[i]->right = vecTree[i * 2 + 2];
		}
	}
	return root;
}
```
### 举例：二叉树的层序遍历完整测试代码
```c++

```
## 遍历系列
[144.二叉树的前序遍历]() 
