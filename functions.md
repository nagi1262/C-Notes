# Functions

## 1. What is a Function?

A function is a block of code designed to perform a specific task.

Functions help us:

* Avoid repeating code
* Organize programs
* Make code easier to read
* Make debugging easier
* Break large problems into smaller parts

Example:

```c
#include <stdio.h>

void greet() {
    printf("Hello!");
}

int main() {
    greet();
    return 0;
}
```

---

## 2. Types of Functions

Functions can be broadly divided into:

1. Library functions
2. User-defined functions

### Library Functions

These are provided by C libraries.

Examples:

```c
printf();
scanf();
strlen();
sqrt();
```

### User-defined Functions

These are created by the programmer.

```c
void greet() {
    printf("Hello!");
}
```

---

## 3. Function Syntax

```c
return_type function_name(parameters) {
    // statements
}
```

Example:

```c
int add(int a, int b) {
    return a + b;
}
```

Here:

* `int` → return type
* `add` → function name
* `a` and `b` → parameters
* `return` → sends a value back

---

## 4. Function Prototype

A function can be declared before it is used.

```c
int add(int, int);
```

This is called a **function prototype**.

Example:

```c
#include <stdio.h>

int add(int, int);

int main() {
    printf("%d", add(5, 3));
    return 0;
}

int add(int a, int b) {
    return a + b;
}
```

The prototype tells the compiler about the function before its definition is encountered.

---

## 5. Function Definition

The actual implementation of a function is called its definition.

```c
int add(int a, int b) {
    return a + b;
}
```

---

## 6. Function Call

A function is executed by calling it.

```c
add(5, 3);
```

Example:

```c
int result = add(5, 3);
```

Here, `result` becomes `8`.

---

## 7. Parameters and Arguments

### Parameters

Variables written in the function definition:

```c
int add(int a, int b)
```

Here, `a` and `b` are parameters.

### Arguments

Actual values passed during the function call:

```c
add(5, 3);
```

Here, `5` and `3` are arguments.

---

## 8. Function With No Return Value

Use `void` when a function does not return a value.

```c
void greet() {
    printf("Hello!");
}
```

Call:

```c
greet();
```

---

## 9. Function With a Return Value

```c
int square(int n) {
    return n * n;
}
```

Use:

```c
int result = square(5);
```

`result` becomes `25`.

---

## 10. Function With Parameters

```c
int add(int a, int b) {
    return a + b;
}
```

Call:

```c
int result = add(10, 20);
```

Output:

```text
30
```

---

## 11. Pass by Value

In a normal C function call, arguments are passed by value.

The function receives a copy of the value.

```c
void change(int x) {
    x = 100;
}

int main() {
    int a = 10;

    change(a);

    printf("%d", a);
}
```

Output:

```text
10
```

Changing `x` does not change `a`.

---

## 12. Local Variables

Variables declared inside a function are local to that function.

```c
void test() {
    int x = 10;
}
```

`x` cannot normally be accessed directly from another function.

---

## 13. Global Variables

A variable declared outside all functions can have file scope.

```c
#include <stdio.h>

int count = 10;

void display() {
    printf("%d", count);
}

int main() {
    display();
    return 0;
}
```

Avoid unnecessary global variables because they can make programs harder to understand and maintain.

---

## 14. Recursion

When a function calls itself, it is called **recursion**.

Example:

```c
int factorial(int n) {
    if (n <= 1) {
        return 1;
    }

    return n * factorial(n - 1);
}
```

For:

```c
factorial(5)
```

the result is:

```text
120
```

A recursive function needs a **base case** to stop recursion.

---

## 15. Example: Find Maximum

```c
#include <stdio.h>

int maximum(int a, int b) {
    if (a > b)
        return a;
    else
        return b;
}

int main() {
    int result = maximum(10, 20);

    printf("Maximum = %d", result);

    return 0;
}
```

Output:

```text
Maximum = 20
```

---

## 16. Common Mistakes

### Forgetting `return`

Wrong:

```c
int add(int a, int b) {
    a + b;
}
```

Correct:

```c
int add(int a, int b) {
    return a + b;
}
```

### Calling a Function Before Declaring It

If the function definition appears later, provide a prototype:

```c
int add(int, int);
```

### Confusing Parameters and Arguments

```c
int add(int a, int b)  // parameters

add(5, 3);             // arguments
```

---

## Quick Revision

```text
Function declaration  → tells compiler about function
Function definition   → contains function code
Function call         → executes the function
Parameter             → variable in function definition
Argument              → value passed to function
return                → sends a value back
void                  → no return value
recursion             → function calls itself
```
