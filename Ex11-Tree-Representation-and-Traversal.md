# Ex11 Tree Representation and Traversal
## DATE:
## AIM:
To write a C function to perform post order traversal of a binary tree.

## Algorithm
1.Start the program
2.Define a structure for tree node (data, left, right)
3.Create nodes and build the binary tree
4.Define a recursive function for postorder traversal
5.Traverse: Left → Right → Root
6.Print node values during traversal
7.Stop  

## Program:
```
/*
Program to perform post order traversal of a binary tree
Developed by: SANGAVI S
RegisterNumber: 212222230130
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

// Postorder Traversal
void postorder(struct node* root)
{
    if(root != NULL)
    {
        postorder(root->left);
        postorder(root->right);
        printf("%d ", root->data);
    }
}

int main()
{
    struct node* root;

    // Creating tree
    root = newNode(1);
    root->left = newNode(2);
    root->right = newNode(3);
    root->left->left = newNode(4);
    root->left->right = newNode(5);

    printf("Postorder Traversal:\n");
    postorder(root);

    return 0;
}
```

## Output:
<img width="446" height="186" alt="image" src="https://github.com/user-attachments/assets/702c1752-a8fe-49c2-91a4-9d5e49c53d8d" />



## Result:
Thus, the function to perform post order traversal of a binary tree is implemented successfully
