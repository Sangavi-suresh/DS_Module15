# Ex15 Largest Element in BST
## DATE:
## AIM:
To Write a c program to find the largest value in a Binary Search Tree.

## Algorithm
1.Start the program
2.Define structure for BST node (data, left, right)
3.Insert elements into the BST
4.Traverse to the rightmost node (largest element)
5.Display the value of the rightmost node
6.Stop

## Program:
```
/*
Program to find the largest value in a Binary Search Tree
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

// Insert into BST
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

// Find largest element
int findMax(struct node* root)
{
    if(root == NULL)
        return -1;

    while(root->right != NULL)
    {
        root = root->right;
    }
    return root->data;
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

    printf("Largest element in BST: %d", findMax(root));

    return 0;
}
```

## Output:

<img width="553" height="222" alt="image" src="https://github.com/user-attachments/assets/4a7c82ec-0224-4a8c-9a76-eb0a07952e5d" />


## Result:
Thus, the C program to find the largest value in a Binary Search Tree is implemented successfully.
