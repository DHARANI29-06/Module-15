# Ex. No: 15B - Build a Binary Search Tree Using Built-in Function

## AIM:
To write a Python program to build a binary search tree using a built-in function.
## ALGORITHM:

1. **Start the program.**
2. Define `_build_bst_from_sorted_values(sorted_values)` to recursively build a binary search tree (BST) from a sorted list.
3. Define `left_subtree(l)` to print the left subtree of the BST.
4. Take user input for the number of elements and store the values in a list `a`.
5. Sort the list and pass it to `_build_bst_from_sorted_values()` to construct the BST.
6. Print the postorder traversal of the BST.
7. Call `left_subtree(l)` to print the left subtree.
8. Check whether the tree is a binary search tree using the `is_bst` property.
9. **End the program.**
## PROGRAM:

```
from binarytree import Node
def _build_bst_from_sorted_values(sorted_values):
    if not sorted_values:
        return None
    else:
        mid=len(sorted_values)//2
        root=Node(sorted_values[mid])
        root.left=_build_bst_from_sorted_values(sorted_values[:mid])
        root.right=_build_bst_from_sorted_values(sorted_values[mid + 1 :])
    return (root)


def left_subtree(l):
    print("Left Subtree :")
    for i in l.left.values:
        print(f"{i} -->",end="")
    print()
size=int(input())
a=[int(input()) for i in range(size)]
a=sorted(a)
btree=_build_bst_from_sorted_values(a)
print(f"Postorder : {list(btree.postorder)}")
left_subtree(btree)
print(f"Is this a Binary Search Tree?  {btree.is_bst}")
```

## OUTPUT
![image](https://github.com/user-attachments/assets/9c599325-95ed-4e4b-b03c-1c7debfa0689)
## RESULT
Thus , a Python program to build a binary search tree using a built-in function are verified.
