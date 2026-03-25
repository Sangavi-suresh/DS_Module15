# Ex13 Expression Tree
## DATE:
## AIM:
To write a C function to construct an Expression Tree for the given Postfix Expression and display the output in the format of In-order ,Pre-order and Post-order traversal.

## Algorithm
1.Start the program
2.Read postfix expression
3.Create an empty stack
4.For each symbol in postfix expression:
5.If operand → create node and push to stack
6.If operator → pop two nodes, create new node, push back
7.Final node in stack is root of expression tree
8.Perform inorder, preorder, and postorder traversals
9.Display results
10.Stop   

## Program:
```
/*
Program to construct Expression Tree from Postfix Expression
Developed by: SANGAVI S
RegisterNumber: 212222230130
*/

#include<stdio.h>
#include<stdlib.h>
#include<ctype.h>

struct node
{
    char data;
    struct node *left, *right;
};

struct node* stack[50];
int top = -1;

// Push
void push(struct node* n)
{
    stack[++top] = n;
}

// Pop
struct node* pop()
{
    return stack[top--];
}

// Create node
struct node* newNode(char val)
{
    struct node* temp = (struct node*)malloc(sizeof(struct node));
    temp->data = val;
    temp->left = temp->right = NULL;
    return temp;
}

// Build Expression Tree
struct node* buildTree(char postfix[])
{
    int i;
    char ch;

    for(i = 0; postfix[i] != '\0'; i++)
    {
        ch = postfix[i];

        if(isalnum(ch)) // operand
        {
            push(newNode(ch));
        }
        else // operator
        {
            struct node* t = newNode(ch);
            t->right = pop();
            t->left = pop();
            push(t);
        }
    }
    return pop();
}

// Traversals
void inorder(struct node* root)
{
    if(root != NULL)
    {
        inorder(root->left);
        printf("%c ", root->data);
        inorder(root->right);
    }
}

void preorder(struct node* root)
{
    if(root != NULL)
    {
        printf("%c ", root->data);
        preorder(root->left);
        preorder(root->right);
    }
}

void postorder(struct node* root)
{
    if(root != NULL)
    {
        postorder(root->left);
        postorder(root->right);
        printf("%c ", root->data);
    }
}

int main()
{
    char postfix[50];

    printf("Enter postfix expression: ");
    scanf("%s", postfix);

    struct node* root = buildTree(postfix);

    printf("\nInorder Traversal: ");
    inorder(root);

    printf("\nPreorder Traversal: ");
    preorder(root);

    printf("\nPostorder Traversal: ");
    postorder(root);

    return 0;
}
```

## Output:
<img width="495" height="270" alt="image" src="https://github.com/user-attachments/assets/5bce616b-88cb-48ac-b89c-406be19eea78" />



## Result:
Thus, the C program to display the Expression Tree in the format of In-order ,Pre-order and Post-order traversal.
