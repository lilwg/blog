## This is my first blog post

```python
def createBinaryTree(self, descriptions: List[List[int]]) -> Optional[TreeNode]:
    nodes = defaultdict(TreeNode)
    parents = set()
    children = set()
    for p, c, isLeft in descriptions:
        nodes[p].val = p
        nodes[c].val = c
        if isLeft == 1:
            nodes[p].left = nodes[c]
        else:
            nodes[p].right = nodes[c]
        parents.add(nodes[p])
        children.add(nodes[c])

    return (parents - children).pop()
```
