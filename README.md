# Sorting-Algorithm-Visualizer

A Sorting Algorithm Visualizer is a program that visually demonstrates how different sorting algorithms arrange data step by step. It helps users understand the working process, comparisons, and swaps performed during sorting.

---

# Project Information

- Project Title: Sorting Algorithm Visualizer
- Department: Computer Science and Engineering
- Academic Year: 2025–26
- Technology Used: C++
- Type: Console Application

---

# Main Purpose

* Makes sorting algorithms easy to learn visually.
* Shows how elements move during sorting.
* Helps compare efficiency and behavior of algorithms.

---

# Common Features

* Generate random array/data
* Visual bars or numbers representing elements
* Animation of sorting process
* Start, pause, and reset controls
* Speed adjustment
* Comparison counter and swap counter
  

---

# Working Principle

1. Random values are generated.
2. Each value is represented as a bar or box.
3. During sorting:

   * Comparisons are highlighted
   * Swaps are animated
   * Sorted elements change color
4. Final sorted array is displayed.

---

# Technologies Used

## Console-Based Application

* C++
* Arrays
* Delay functions (`sleep`)
* ASCII graphics / text output

---

# How to Run

## Step 1

Save the source code as:

```bash
sorting_visualizer.cpp
```

## Step 2

Compile the code:

```bash
g++ sorting_visualizer.cpp -o sorting_visualizer
```

## Step 3

Run the program:

```bash
./sorting_visualizer
```
## Full Source Code

```cpp
// SORTING ALGORITHM VISUALIZER (Console Based)
// Developed using C++

#include <iostream>
#include <windows.h>
#include <iomanip>
using namespace std;

// Function to display array as bars
void display(int arr[], int n)
{
    system("cls");

    cout << "\n\n\tSORTING ALGORITHM VISUALIZER\n\n";

    for(int i = 0; i < n; i++)
    {
        cout << setw(2) << arr[i] << " : ";

        for(int j = 0; j < arr[i]; j++)
        {
            cout << char(219);
        }

        cout << endl;
    }

    Sleep(300);
}

// Bubble Sort
void bubbleSort(int arr[], int n)
{
    for(int i = 0; i < n - 1; i++)
    {
        for(int j = 0; j < n - i - 1; j++)
        {
            if(arr[j] > arr[j + 1])
            {
                swap(arr[j], arr[j + 1]);
                display(arr, n);
            }
        }
    }

    cout << "\n\nBubble Sort Completed!\n";
}

// Selection Sort
void selectionSort(int arr[], int n)
{
    for(int i = 0; i < n - 1; i++)
    {
        int minIndex = i;

        for(int j = i + 1; j < n; j++)
        {
            if(arr[j] < arr[minIndex])
            {
                minIndex = j;
            }
        }

        swap(arr[i], arr[minIndex]);
        display(arr, n);
    }

    cout << "\n\nSelection Sort Completed!\n";
}

// Insertion Sort
void insertionSort(int arr[], int n)
{
    for(int i = 1; i < n; i++)
    {
        int key = arr[i];
        int j = i - 1;

        while(j >= 0 && arr[j] > key)
        {
            arr[j + 1] = arr[j];
            j--;
            display(arr, n);
        }

        arr[j + 1] = key;
        display(arr, n);
    }

    cout << "\n\nInsertion Sort Completed!\n";
}

// Partition Function for Quick Sort
int partition(int arr[], int low, int high, int n)
{
    int pivot = arr[high];
    int i = low - 1;

    for(int j = low; j < high; j++)
    {
        if(arr[j] < pivot)
        {
            i++;
            swap(arr[i], arr[j]);
            display(arr, n);
        }
    }

    swap(arr[i + 1], arr[high]);
    display(arr, n);

    return i + 1;
}

// Quick Sort
void quickSort(int arr[], int low, int high, int n)
{
    if(low < high)
    {
        int pi = partition(arr, low, high, n);

        quickSort(arr, low, pi - 1, n);
        quickSort(arr, pi + 1, high, n);
    }
}

// Main Function
int main()
{
    int n, choice;

    cout << "\nEnter number of elements: ";
    cin >> n;

    int arr[n];

    cout << "\nEnter array elements:\n";

    for(int i = 0; i < n; i++)
    {
        cin >> arr[i];
    }

    cout << "\n===== SORTING MENU =====\n";
    cout << "1. Bubble Sort\n";
    cout << "2. Selection Sort\n";
    cout << "3. Insertion Sort\n";
    cout << "4. Quick Sort\n";
    cout << "Enter your choice: ";
    cin >> choice;

    display(arr, n);

    switch(choice)
    {
        case 1:
            bubbleSort(arr, n);
            break;

        case 2:
            selectionSort(arr, n);
            break;

        case 3:
            insertionSort(arr, n);
            break;

        case 4:
            quickSort(arr, 0, n - 1, n);
            cout << "\n\nQuick Sort Completed!\n";
            break;

        default:
            cout << "\nInvalid Choice!";
    }

    cout << "\n\nFinal Sorted Array:\n";

    for(int i = 0; i < n; i++)
    {
        cout << arr[i] << " ";
    }

    cout << endl;

    return 0;
}
```
---

# Time Complexity Analysis

| Algorithm      | Best Case  | Average Case | Worst Case |
| -------------- | ---------- | ------------ | ---------- |
| Bubble Sort    | O(n)       | O(n²)        | O(n²)      |
| Selection Sort | O(n²)      | O(n²)        | O(n²)      |
| Insertion Sort | O(n)       | O(n²)        | O(n²)      |
| Quick Sort     | O(n log n) | O(n log n)   | O(n²)      |


---

# Concepts Used

## Data Structures

* Arrays

---

## Algorithms

* Bubble Sort
* Selection Sort
* Insertion Sort
* Quick Sort

---

## Programming Concepts

* Functions
* Recursion
* Loops
* Conditional Statements
* Swapping
* Modular Programming

---

## Visualization Concepts

* ASCII Graphics
* Animation Delay
* Console Screen Refresh
  
---



# Advantages

* Improves algorithm understanding
* Useful for students and beginners
* Helps analyze time complexity practically

---

# Applications

* Educational tools
* DSA learning platforms
* College mini projects
* Interview preparation

---

# Team Members

1. Bandaru Tanishq Reddy (EG)
2. Palle Akanksha (CA)
3. Akkapelli Akhil (CB)
4. Ansh Patel (CG)
5. Badavath Raghavulu (DM)

---

# Conclusion

The Sorting Algorithm Visualizer is a console-based C++ project that visually demonstrates sorting algorithms step by step. It helps users understand sorting operations, comparisons, and swaps in an interactive way. The project is useful for learning Data Structures and Algorithms practically.


