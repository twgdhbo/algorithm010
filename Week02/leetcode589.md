#### [N叉树的前序遍历](https://leetcode-cn.com/problems/n-ary-tree-preorder-traversal/)

### solution 1

```java
/*
// Definition for a Node.
class Node {
    public int val;
    public List<Node> children;

    public Node() {}

    public Node(int _val) {
        val = _val;
    }

    public Node(int _val, List<Node> _children) {
        val = _val;
        children = _children;
    }
};
*/

class Solution {
    public List<Integer> preorder(Node root) {
        List<Integer> res = new ArrayList<>();
        if (root == null) {
            return res;
        }
        helper(root, res);
        return res;    
    }

    public void helper(Node root, List<Integer> res) {
        if (root == null) {return;}
        res.add(root.val);
        for (Node node : root.children) {
            helper(node, res);
        }
    }
}
```

comment: