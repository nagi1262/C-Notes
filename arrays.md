# Arrays

## 1. What is an Array?

An array is a collection of elements of the **same data type** stored in contiguous memory locations.

Example:

```c
int marks[5];
```

This creates an array that can store 5 integers.

---

## 2. Array Declaration

Syntax:

```c
data_type array_name[size];
```

Examples:

```c
int numbers[5];
float prices[10];
char letters[4];
```

---

## 3. Array Indexing

C arrays use **zero-based indexing**.

For:

```c
int numbers[5];
```

the indexes are:

```text
Index:   0   1   2   3   4
         ↓   ↓   ↓   ↓   ↓
       [10][20][30][40][50]
```

The last valid index is:

```text
size - 1
```

---

## 4. Array Initialization

### Full Initialization

```c
int numbers[5] = {10, 20, 30, 40, 50};
```

### Partial Initialization

```c
int numbers[5] = {10, 20};
```

The remaining elements are initialized to zero.

Conceptually:

```text
10 20 0 0 0
```

### Size Inferred From Initializer

```c
int numbers[] = {10, 20, 30};
```

The compiler determines the size as `3`.

---

## 5. Accessing and Modifying Elements

```c
int numbers[3] = {10, 20, 30};

printf("%d", numbers[1]);

numbers[1] = 50;
```

The array becomes:

```text
10 50 30
```

---

## 6. Taking Array Input

```c
int numbers[5];

for (int i = 0; i < 5; i++) {
    scanf("%d", &numbers[i]);
}
```

Each element is entered separately.

---

## 7. Printing an Array

```c
for (int i = 0; i < 5; i++) {
    printf("%d ", numbers[i]);
}
```

---

## 8. Example: Sum of Array Elements

```c
#include <stdio.h>

int main() {
    int numbers[5] = {10, 20, 30, 40, 50};
    int sum = 0;

    for (int i = 0; i < 5; i++) {
        sum += numbers[i];
    }

    printf("Sum = %d", sum);

    return 0;
}
```

Output:

```text
Sum = 150
```

---

## 9. Finding the Maximum

```c
int numbers[5] = {12, 45, 7, 31, 20};

int max = numbers[0];

for (int i = 1; i < 5; i++) {
    if (numbers[i] > max) {
        max = numbers[i];
    }
}

printf("Maximum = %d", max);
```

---

## 10. Finding the Minimum

```c
int min = numbers[0];

for (int i = 1; i < 5; i++) {
    if (numbers[i] < min) {
        min = numbers[i];
    }
}
```

---

## 11. Finding Array Size Using `sizeof`

For an actual array in the same scope:

```c
int numbers[] = {10, 20, 30, 40};

int size = sizeof(numbers) / sizeof(numbers[0]);
```

Here:

```text
sizeof(numbers)     → total size of the array in bytes
sizeof(numbers[0])  → size of one element
```

Therefore:

```text
size = number of elements
```

---

## 12. Character Arrays / Strings

A string in C is represented by a character array ending with a null character `\0`.

```c
char name[] = "Aditya";
```

Conceptually:

```text
A d i t y a \0
```

The null character marks the end of the string.

---

## 13. Two-Dimensional Arrays

A 2D array can be thought of as rows and columns.

Declaration:

```c
int matrix[2][3];
```

This has:

```text
2 rows
3 columns
```

Example:

```c
int matrix[2][3] = {
    {1, 2, 3},
    {4, 5, 6}
};
```

Access:

```c
matrix[0][0]  // 1
matrix[1][2]  // 6
```

---

## 14. Traversing a 2D Array

Use nested loops:

```c
for (int i = 0; i < 2; i++) {
    for (int j = 0; j < 3; j++) {
        printf("%d ", matrix[i][j]);
    }

    printf("\n");
}
```

Output:

```text
1 2 3
4 5 6
```

---

## 15. Passing Arrays to Functions

Arrays can be passed to functions.

```c
void printArray(int arr[], int size) {
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
}
```

Call:

```c
int numbers[] = {10, 20, 30};

printArray(numbers, 3);
```

The size is commonly passed separately.

---

## 16. Array and Memory

Array elements are stored next to each other in memory.

For example:

```c
int numbers[3] = {10, 20, 30};
```

Conceptually:

```text
numbers[0] → first element
numbers[1] → next element
numbers[2] → next element
```

---

## 17. Common Mistakes

### Going Outside Array Bounds

Wrong:

```c
int numbers[5];

numbers[5] = 10;
```

Valid indexes are:

```text
0 1 2 3 4
```

`numbers[5]` is outside the array.

### Off-by-One Error

Correct:

```c
for (int i = 0; i < 5; i++)
```

Be careful with:

```c
i <= 5
```

because it attempts to access index `5`.

### Forgetting `&` With `scanf`

Correct:

```c
scanf("%d", &numbers[i]);
```

---

## Quick Revision

```text
Array       → collection of same-type elements
Index       → starts from 0
Last index  → size - 1
arr[i]      → access element
2D array    → rows × columns
sizeof      → useful for finding array size in its original scope
```

Remember:

```c
int a[5];
```

has valid indexes:

```text
0, 1, 2, 3, 4
```
