# C Basics

## 1. What is C?
C is a general-purpose, procedural programming language widely used for system programming, embedded systems, operating systems, and learning programming fundamentals.

## 2. Basic C Program
```c
#include <stdio.h>

int main() {
    printf("Hello, World!");
    return 0;
}
```

- `#include <stdio.h>` → includes standard input/output functions.
- `main()` → program entry point.
- `{ }` → code block.
- `printf()` → prints output.
- `return 0;` → successful termination.
- `;` → ends a statement.

## 3. Comments
```c
// Single-line comment

/*
   Multi-line comment
*/
```

## 4. Variables
A variable is a named memory location used to store data.

```c
int age = 18;
float marks = 85.5f;
char grade = 'A';
```

## 5. Data Types

| Type | Typical size* | Example |
|---|---:|---|
| `char` | 1 byte | `'A'` |
| `int` | 4 bytes | `25` |
| `float` | 4 bytes | `3.14f` |
| `double` | 8 bytes | `3.14159` |
| `void` | — | no value |

*Exact sizes depend on the implementation.

### Format Specifiers
| Type | Specifier |
|---|---|
| `int` | `%d` |
| `char` | `%c` |
| `float` | `%f` |
| `double` | `%lf` in `scanf` |
| `long` | `%ld` |
| `long long` | `%lld` |

## 6. Input and Output

### Output
```c
int age = 18;
printf("Age = %d", age);
```

### Input
```c
int age;
scanf("%d", &age);
```

`&` supplies the address of the variable to `scanf()`.

Multiple inputs:
```c
int a, b;
scanf("%d %d", &a, &b);
```

For a character:
```c
char ch;
scanf(" %c", &ch);
```

## 7. Escape Sequences

| Escape | Meaning |
|---|---|
| `\n` | newline |
| `\t` | tab |
| `\\` | backslash |
| `\"` | double quote |
| `\'` | single quote |

## 8. Constants
```c
const int DAYS = 7;
```
A `const` object should not be modified after initialization.

## 9. Type Casting
```c
int a = 5, b = 2;
float result = (float)a / b;
```
Casting changes how a value is interpreted for an expression.

## 10. `sizeof`
Returns the size of a type or object in bytes.
```c
printf("%zu", sizeof(int));
```

## 11. Identifiers
Rules:
- Can contain letters, digits, and `_`.
- Cannot start with a digit.
- Cannot be a keyword.
- C is case-sensitive.

Valid: `age`, `student_name`, `num1`

Invalid: `1num`, `student-name`, `int`

## 12. Keywords
Examples:
```text
int  char  float  double  if  else  for  while
return  void  switch  case  break  continue
```

## 13. Basic Example
```c
#include <stdio.h>

int main() {
    int a, b, sum;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    sum = a + b;

    printf("Sum = %d\n", sum);
    return 0;
}
```

## Quick Revision
- `main()` is the normal entry point of a C program.
- Statements generally end with `;`.
- `=` is assignment; `==` is comparison.
- `scanf()` normally needs addresses for ordinary variables.
- C is case-sensitive.
