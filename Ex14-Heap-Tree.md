<img width="495" height="270" alt="image" src="https://github.com/user-attachments/assets/d11636c8-dc8c-45c7-9514-d52acd2a5848" /># Ex14 Heap Tree
## DATE:
## AIM:
To write a C function to delete an element in a Heap Tree.

## Algorithm
1.Start the program
2.Create a heap using an array representation
3.Insert elements into the heap
4.Delete root element (maximum/minimum):
5.Replace root with last element
6.Reduce heap size
7.Heapify the root to maintain heap property
8.Display the heap after deletion
9.Stop  

## Program:
```
/*
Program to delete an element in a Heap Tree
Developed by: SANGAVI S
RegisterNumber: 212222230130
*/

#include<stdio.h>

void heapify(int arr[], int n, int i)
{
    int largest = i;
    int left = 2 * i + 1;
    int right = 2 * i + 2;
    int temp;

    if(left < n && arr[left] > arr[largest])
        largest = left;

    if(right < n && arr[right] > arr[largest])
        largest = right;

    if(largest != i)
    {
        temp = arr[i];
        arr[i] = arr[largest];
        arr[largest] = temp;

        heapify(arr, n, largest);
    }
}

// Delete root element
void deleteRoot(int arr[], int *n)
{
    arr[0] = arr[*n - 1];
    (*n)--;

    heapify(arr, *n, 0);
}

// Display heap
void display(int arr[], int n)
{
    for(int i = 0; i < n; i++)
        printf("%d ", arr[i]);
}

int main()
{
    int arr[50] = {50, 30, 40, 10, 20, 35};
    int n = 6;

    printf("Heap before deletion:\n");
    display(arr, n);

    deleteRoot(arr, &n);

    printf("\nHeap after deletion:\n");
    display(arr, n);

    return 0;
}
```

## Output:
<img width="479" height="267" alt="image" src="https://github.com/user-attachments/assets/5db4a2fe-0632-47e9-9401-89e34a69dbad" />



## Result:
Thus, the function to delete an element in a Heap Tree is implemented successfully.
