# Pointers

## 1. What is a Pointer?

A pointer is a variable that stores the **memory address** of another object.

Example:

```c
int x = 10;
int *p = &x;
```

Here:

* `x` stores `10`.
* `&x` gives the address of `x`.
* `p` stores that address.
* `*p` accesses the value stored at that address.

---

## 2. Why Use Pointers?

Pointers are important for:

* Working with memory
* Passing values to functions by address
* Modifying variables inside functions
* Working with arrays and strings
* Dynamic memory allocation
* Data structures such as linked lists and trees

---

## 3. Pointer Declaration

Syntax:

```c
data_type *pointer_name;
```

Examples:

```c
int *p;
char *c;
float *f;
```

The pointer type indicates the type of object the pointer is intended to point to.

---

## 4. Address-of Operator `&`

The `&` operator obtains the address of an object.

```c
int x = 10;

printf("%p", (void *)&x);
```

The exact address varies between program executions and systems.

---

## 5. Dereference Operator `*`

The `*` operator can be used to access the value stored at the address held by a pointer.

```c
int x = 10;
int *p = &x;

printf("%d", *p);
```

Output:

```text
10
```

Remember:

```text
&x → address of x
p  → stores address of x
*p → value stored at that address
```

---

## 6. Changing a Value Through a Pointer

```c
int x = 10;
int *p = &x;

*p = 50;

printf("%d", x);
```

Output:

```text
50
```

Because `p` points to `x`, changing `*p` changes `x`.

---

## 7. Pointer and Data Type

The pointer type should be appropriate for the object it points to.

```c
int x = 10;
int *p = &x;
```

```c
char ch = 'A';
char *p = &ch;
```

---

## 8. NULL Pointer

A null pointer does not point to a valid object.

```c
int *p = NULL;
```

Check before dereferencing when necessary:

```c
if (p != NULL) {
    printf("%d", *p);
}
```

Never dereference a `NULL` pointer.

---

## 9. Pointers and Functions

Pointers allow a function to modify the caller's variable.

Example:

```c
void change(int *x) {
    *x = 100;
}

int main() {
    int a = 10;

    change(&a);

    printf("%d", a);

    return 0;
}
```

Output:

```text
100
```

### What happens?

Call:

```c
change(&a);
```

The address of `a` is passed.

Inside the function:

```c
*x = 100;
```

changes the original variable.

---

## 10. Swapping Two Numbers Using Pointers

```c
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}
```

Call:

```c
int x = 10;
int y = 20;

swap(&x, &y);
```

After the call:

```text
x = 20
y = 10
```

---

## 11. Pointers and Arrays

The name of an array often acts as a pointer to its first element when used in an expression.

Example:

```c
int arr[3] = {10, 20, 30};

int *p = arr;
```

Here, `p` points to `arr[0]`.

```c
printf("%d", *p);
```

Output:

```text
10
```

---

## 12. Pointer Arithmetic

Pointers can be incremented and decremented.

```c
int arr[] = {10, 20, 30};

int *p = arr;

printf("%d", *p);  // 10

p++;

printf("%d", *p);  // 20
```

For an `int *`, incrementing moves to the next `int` element.

---

## 13. Array Access Using Pointers

For an array `arr`:

```c
arr[i]
```

corresponds to:

```c
*(arr + i)
```

Example:

```c
int arr[] = {10, 20, 30};

printf("%d", arr[1]);
printf("%d", *(arr + 1));
```

Both print:

```text
20
```

---

## 14. Pointer to Pointer

A pointer can store the address of another pointer.

```c
int x = 10;
int *p = &x;
int **pp = &p;
```

Conceptually:

```text
x   → 10
↑
p   → address of x
↑
pp  → address of p
```

Access:

```c
*p    // 10
**pp  // 10
```

---

## 15. `const` and Pointers

### Pointer to Constant Data

```c
const int *p = &x;
```

You cannot modify `x` through `p`.

### Constant Pointer

```c
int *const p = &x;
```

The pointer itself cannot be changed to point somewhere else after initialization.

### Both Constant

```c
const int *const p = &x;
```

Neither the pointed-to value nor the pointer itself can be modified through `p`.

---

## 16. Common Pointer Mistakes

### Uninitialized Pointer

Wrong:

```c
int *p;

*p = 10;
```

`p` does not point to a valid object.

Correct:

```c
int x;

int *p = &x;

*p = 10;
```

### Dereferencing `NULL`

Wrong:

```c
int *p = NULL;

printf("%d", *p);
```

This causes undefined behavior.

### Invalid Pointer

Only dereference a pointer when it points to a valid object.

---

## 17. Pointer vs Normal Variable

| Normal Variable    | Pointer                        |
| ------------------ | ------------------------------ |
| Stores a value     | Stores an address              |
| `x`                | `p`                            |
| `x = 10`           | `p = &x`                       |
| `x` gives value    | `*p` accesses pointed-to value |
| `&x` gives address | `p` contains that address      |

---

## 18. Example: Array Traversal Using a Pointer

```c
#include <stdio.h>

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int *p = arr;

    for (int i = 0; i < 5; i++) {
        printf("%d ", *(p + i));
    }

    return 0;
}
```

Output:

```text
10 20 30 40 50
```

---

## Quick Revision

```text
Pointer       → stores an address
&variable     → gets address
*pointer      → accesses pointed-to value
NULL          → points to no valid object
p++           → moves to next element of the pointer's type
arr[i]        → *(arr + i)
int **pp      → pointer to pointer
```

### Golden Rule

Before dereferencing a pointer, make sure it points to a valid object:

```c
if (p != NULL) {
    printf("%d", *p);
}
```
