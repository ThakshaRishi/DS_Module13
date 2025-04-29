# Ex2 Conversion of the infix expression into postfix expression
## DATE: 5.03.2024
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm

1. Start with the root node.

2. If the tree is empty, create a new node as the root.

3. Else, compare the value to be inserted with the current node:

      -If it is smaller, recursively insert in the left subtree.

      -If it is greater, recursively insert in the right subtree.

4. Repeat until the correct position is found.

5. Insert the new node at that position.   

## Program:
```
/*
Program to insert the elements in the binary search tree
Developed by: Thaksha Rishi
RegisterNumber: 212223100058
*/

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* left;
    struct Node* right;
};

struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->left = NULL;
    newNode->right = NULL;
    return newNode;
}

struct Node* insert(struct Node* root, int value) {
    if (root == NULL) {
        return createNode(value);
    }

    if (value < root->data) {
        root->left = insert(root->left, value);
    } else if (value > root->data) {
        root->right = insert(root->right, value);
    }

    return root;
}

void inOrderTraversal(struct Node* root) {
    if (root == NULL)
        return;
    inOrderTraversal(root->left);
    printf("%d ", root->data);
    inOrderTraversal(root->right);
}

int main() {
    struct Node* root = NULL;

    root = insert(root, 50);
    insert(root, 30);
    insert(root, 70);
    insert(root, 20);
    insert(root, 40);
    insert(root, 60);
    insert(root, 80);

    printf("Inorder traversal of the BST:\n");
    inOrderTraversal(root);

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/8e389be3-101b-47fc-91ac-b900f37fd3fb)


## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
