### Algorithm：每周至少做一个 leetcode 的算法题
给定两个二叉树，想象当你将它们中的一个覆盖到另一个上时，两个二叉树的一些节点便会重叠。

你需要将他们合并为一个新的二叉树。合并的规则是如果两个节点重叠，那么将他们的值相加作为节点合并后的新值，否则不为 NULL 的节点将直接作为新二叉树的节点。

示例 1:

输入: 
	Tree 1                     Tree 2                  
          1                         2                             
         / \                       / \                            
        3   2                     1   3                        
       /                           \   \                      
      5                             4   7                  
输出: 
合并后的树:
	     3
	    / \
	   4   5
	  / \   \ 
	 5   4   7
注意: 合并必须从两个树的根节点开始。
 
 
 
 /**
  * Definition for a binary tree node.
  * public class TreeNode {
  *     int val;
  *     TreeNode left;
  *     TreeNode right;
  *     TreeNode(int x) { val = x; }
  * }
  */
 class Solution {
     public TreeNode mergeTrees(TreeNode t1, TreeNode t2) {
        public TreeNode mergeTrees(TreeNode t1, TreeNode t2) {
                if (t1 == null)
                    return t2;
                Stack < TreeNode[] > stack = new Stack < > ();
                stack.push(new TreeNode[] {t1, t2});
                while (!stack.isEmpty()) {
                    TreeNode[] t = stack.pop();
                    if (t[0] == null || t[1] == null) {
                        continue;
                    }
                    t[0].val += t[1].val;
                    if (t[0].left == null) {
                        t[0].left = t[1].left;
                    } else {
                        stack.push(new TreeNode[] {t[0].left, t[1].left});
                    }
                    if (t[0].right == null) {
                        t[0].right = t[1].right;
                    } else {
                        stack.push(new TreeNode[] {t[0].right, t[1].right});
                    }
                }
                return t1;
            } 
     }
 }
 
 复杂度分析
 
 时间复杂度：O(N)O(N)，其中 NN 是两棵树中节点个数的较小值。
 
 空间复杂度：O(N)O(N)，在最坏情况下，栈中会存放 NN 个节点。
 
 
 
### Review：阅读并点评至少一篇英文技术文章


### Tip：学习至少一个技术技巧



### Share：分享一篇有观点和思考的技术文章


