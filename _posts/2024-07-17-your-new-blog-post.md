## This is my first blog post

```python
def getDirections(self, root: Optional[TreeNode], startValue: int, destValue: int) -> str:
    def lca(root, p, q):
        if not root or root.val == p or root.val == q:
            return root
        left = lca(root.left, p, q) 
        right = lca(root.right, p, q)
        if left and right:
            return root
        return left if left else right

    def path(node, t, dir=''):
        if not node: return
        if node.val == t: return dir
        a = path(node.left, t, 'L')
        if a: 
            return a + dir
        a = path(node.right, t, 'R')
        if a: return a + dir

    lca = lca(root, startValue, destValue)
    a, b = path(lca, startValue), path(lca, destValue)

    return 'U'*len(a) + b[::-1]
```
