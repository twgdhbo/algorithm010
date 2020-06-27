#### [全排列](https://leetcode-cn.com/problems/permutations/)

### solution 1

```java
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
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if (root == null) {
            return null;
        }

        List<TreeNode> pList = new ArrayList();
        searchNode(root, pList, p);
        List<TreeNode> qList = new ArrayList();
        searchNode(root, qList, q);

        //对比2个list
        //if (pList.size() >= qList.size()) {
            for (int i = 0 ; i < qList.size(); i++) {
                if ( i == qList.size() - 1 || i == pList.size() - 1 ) {
                    return qList.get(i);
                }else {
                    if (qList.get(i).val != pList.get(i).val) {
                        return qList.get(i - 1);
                    }
                }
            }
        return null; 
    }

    public void searchNode(TreeNode root, List<TreeNode> list,TreeNode node) {
        if(root == null) return;
        list.add(root);
        if(root.val == node.val) return;
        //左子树找
        if(root.left != null) {
            searchNode(root.left, list, node);
        }
        //右子树找
        if(root.right != null) {
            searchNode(root.right, list, node);
        } 
        //
    }

}
//前序遍历找P 把途径记下来放到list， 再前序遍历找Q 放到list对比2个list，遍历较长的list找出数字发生不一样的index的前一个index的值
```

comment:做错了前序遍历取到的不是全是父节点的值