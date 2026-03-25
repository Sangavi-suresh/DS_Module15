# Ex12 Binary Search Tree
## DATE:
## AIM:
To write a C function to insert the elements in the binary search tree

## Algorithm
1.Start the program
2.Define structure for BST node (data, left, right)
3.Create a function to insert elements into BST
4.If tree is empty, create a new node
5.If element < root → insert in left subtree
6.If element > root → insert in right subtree
7.Display tree using inorder traversal
8.Stop  

## Program:
```
/*
Program to insert elements in Binary Search Tree
Developed by: SANGAVI S
RegisterNumber:  212222230130
*/

#include<stdio.h>
#include<stdlib.h>

struct node
{
    int data;
    struct node *left, *right;
};

// Create new node
struct node* newNode(int data)
{
    struct node* temp = (struct node*)malloc(sizeof(struct node));
    temp->data = data;
    temp->left = temp->right = NULL;
    return temp;
}

// Insert function
struct node* insert(struct node* root, int data)
{
    if(root == NULL)
        return newNode(data);

    if(data < root->data)
        root->left = insert(root->left, data);
    else if(data > root->data)
        root->right = insert(root->right, data);

    return root;
}

// Inorder traversal (to display sorted order)
void inorder(struct node* root)
{
    if(root != NULL)
    {
        inorder(root->left);
        printf("%d ", root->data);
        inorder(root->right);
    }
}

int main()
{
    struct node* root = NULL;

    root = insert(root, 50);
    insert(root, 30);
    insert(root, 70);
    insert(root, 20);
    insert(root, 40);
    insert(root, 60);
    insert(root, 80);

    printf("Inorder Traversal of BST:\n");
    inorder(root);

    return 0;
}
```

## Output:
<img width="493" height="273" alt="image" src="https://github.com/user-attachments/assets/e052ceb4-af52-4ba4-b864-51dddb346a3d" />



## Result:
Thus, the C function to insert the elements in the binary search tree is implemented successfully.
