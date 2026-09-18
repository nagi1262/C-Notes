# Conditionals and Loops

## 1. Conditionals
Conditionals let a program make decisions based on conditions.

## 2. `if`
```c
if (condition) {
    // statements
}
```

Example:
```c
if (age >= 18) {
    printf("Adult");
}
```

## 3. `if-else`
```c
if (condition) {
    // true
} else {
    // false
}
```

Example:
```c
if (number % 2 == 0) {
    printf("Even");
} else {
    printf("Odd");
}
```

## 4. `else-if` Ladder
Useful for multiple conditions.

```c
if (marks >= 90) {
    printf("A");
} else if (marks >= 80) {
    printf("B");
} else if (marks >= 70) {
    printf("C");
} else {
    printf("D");
}
```

Conditions are checked from top to bottom.

## 5. Nested `if`
```c
if (age >= 18) {
    if (has_id) {
        printf("Allowed");
    }
}
```

## 6. `switch`
Useful when one expression is compared with multiple constant cases.

```c
switch (day) {
    case 1:
        printf("Monday");
        break;

    case 2:
        printf("Tuesday");
        break;

    default:
        printf("Invalid day");
}
```

### `break`
Without `break`, execution can continue into the next case (fall-through).

### `default`
Runs when no case matches.

## 7. Loops
Loops repeat a block of code.

Main loops:
1. `for`
2. `while`
3. `do-while`

## 8. `for` Loop
Useful when the loop has a clear initialization, condition, and update.

```c
for (initialization; condition; update) {
    // statements
}
```

Example:
```c
for (int i = 1; i <= 5; i++) {
    printf("%d\n", i);
}
```

Execution:
```text
initialization
      ↓
  condition
      ↓
     body
      ↓
    update
      ↓
  condition
      ↓
     ...
```

## 9. `while` Loop
Condition is checked before every iteration.

```c
int i = 1;

while (i <= 5) {
    printf("%d\n", i);
    i++;
}
```

## 10. `do-while` Loop
The body runs at least once because the condition is checked afterward.

```c
int i = 1;

do {
    printf("%d\n", i);
    i++;
} while (i <= 5);
```

Remember the semicolon after the condition.

## 11. Loop Comparison

| Loop | Condition checked | Minimum body executions |
|---|---|---:|
| `for` | before | 0 |
| `while` | before | 0 |
| `do-while` | after | 1 |

## 12. `break`
Immediately exits the nearest loop or `switch`.

```c
for (int i = 1; i <= 10; i++) {
    if (i == 5) {
        break;
    }
    printf("%d ", i);
}
```

Output:
```text
1 2 3 4
```

## 13. `continue`
Skips the rest of the current iteration and proceeds to the next iteration.

```c
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        continue;
    }
    printf("%d ", i);
}
```

Output:
```text
1 2 4 5
```

## 14. Nested Loops
A loop can contain another loop.

```c
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 3; j++) {
        printf("* ");
    }
    printf("\n");
}
```

Output:
```text
* * *
* * *
* * *
```

Common uses:
- Patterns
- Matrices
- 2D arrays
- Comparing combinations

## 15. Infinite Loops

```c
while (1) {
    // runs continuously
}
```

or:
```c
for (;;) {
    // infinite loop
}
```

## 16. Common Loop Mistakes

### Forgetting the update
```c
int i = 1;
while (i <= 5) {
    printf("%d", i);
}
```
`i` never changes, so the loop does not terminate.

### Off-by-one error
```c
for (int i = 0; i < 5; i++)
```
runs 5 times: `0` to `4`.

```c
for (int i = 0; i <= 5; i++)
```
runs 6 times: `0` to `5`.

## 17. Combining Conditions and Loops

Print even numbers from 1 to 10:
```c
for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) {
        printf("%d ", i);
    }
}
```

Output:
```text
2 4 6 8 10
```

## 18. Example: Sum of First N Numbers

```c
#include <stdio.h>

int main() {
    int n, sum = 0;

    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        sum += i;
    }

    printf("Sum = %d\n", sum);
    return 0;
}
```

## 19. Example: Factorial

```c
#include <stdio.h>

int main() {
    int n;
    long long factorial = 1;

    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        factorial *= i;
    }

    printf("Factorial = %lld\n", factorial);
    return 0;
}
```

## 20. Example: Prime Check

```c
#include <stdio.h>

int main() {
    int n;
    int is_prime = 1;

    scanf("%d", &n);

    if (n < 2) {
        is_prime = 0;
    } else {
        for (int i = 2; i * i <= n; i++) {
            if (n % i == 0) {
                is_prime = 0;
                break;
            }
        }
    }

    if (is_prime)
        printf("Prime");
    else
        printf("Not Prime");

    return 0;
}
```

## Quick Revision

### Conditionals
```text
if          → one condition
if-else     → two paths
else-if     → multiple conditions
switch      → multiple fixed cases
```

### Loops
```text
for         → initialization + condition + update
while       → condition checked first
do-while    → body executes before condition check
```

### Control
```text
break       → exit nearest loop/switch
continue    → skip current iteration
```

## Exam Tips
- `=` means assignment; `==` means comparison.
- In C, `0` is false and nonzero values are true.
- Use `break` in `switch` when you do not want fall-through.
- Check initialization, condition, and update carefully.
- Watch for off-by-one errors.
- `do-while` executes its body at least once.
