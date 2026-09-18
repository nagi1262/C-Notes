# Operators in C

## 1. What are Operators?
Operators are symbols used to perform operations on values and variables.

```c
int sum = a + b;
```

Here, `+` is an operator.

## 2. Arithmetic Operators

| Operator | Meaning | Example |
|---|---|---|
| `+` | addition | `a + b` |
| `-` | subtraction | `a - b` |
| `*` | multiplication | `a * b` |
| `/` | division | `a / b` |
| `%` | remainder | `a % b` |

For integers:
```c
5 / 2   // 2
5 % 2   // 1
```

## 3. Relational Operators

| Operator | Meaning |
|---|---|
| `==` | equal |
| `!=` | not equal |
| `>` | greater than |
| `<` | less than |
| `>=` | greater than or equal |
| `<=` | less than or equal |

Example:
```c
if (age >= 18) {
    printf("Adult");
}
```

## 4. Logical Operators

| Operator | Meaning |
|---|---|
| `&&` | logical AND |
| `||` | logical OR |
| `!` | logical NOT |

Example:
```c
if (age >= 18 && age <= 60) {
    printf("Valid range");
}
```

In C, `0` is false and a nonzero value is true.

## 5. Assignment Operators

```c
int x = 10;
```

| Operator | Equivalent |
|---|---|
| `+=` | `x = x + 5` |
| `-=` | `x = x - 5` |
| `*=` | `x = x * 5` |
| `/=` | `x = x / 5` |
| `%=` | `x = x % 5` |

## 6. Increment and Decrement

```c
x++;
x--;
```

`++` increases by 1; `--` decreases by 1.

### Pre vs Post
```c
int x = 5;
int a = x++;   // a = 5, x = 6

int y = 5;
int b = ++y;   // b = 6, y = 6
```

## 7. Ternary Operator

Syntax:
```c
condition ? value_if_true : value_if_false;
```

Example:
```c
int max = (a > b) ? a : b;
```

## 8. Bitwise Operators

| Operator | Meaning |
|---|---|
| `&` | bitwise AND |
| `|` | bitwise OR |
| `^` | bitwise XOR |
| `~` | bitwise NOT |
| `<<` | left shift |
| `>>` | right shift |

Example:
```text
5 = 0101
3 = 0011

5 & 3 = 0001 = 1
```

For positive integers, `5 << 1` gives `10` and `5 >> 1` gives `2`.

## 9. `sizeof`
```c
sizeof(int)
sizeof(variable)
```
Returns size in bytes.

## 10. Address-of and Dereference

These are especially important with pointers.

```c
int x = 10;
int *p = &x;

printf("%d", *p);
```

- `&x` → address of `x`
- `*p` → value stored at the address held by `p`

## 11. Operator Precedence

A simplified order:
```text
()
++
--
*
/
%
+
-
<
<=
>
>=
==
!=
&&
||
?:
=
```

Use parentheses when clarity matters:
```c
result = (a + b) * c;
```

## 12. Short-Circuit Evaluation

For `&&`, if the left side is false, the right side may not be evaluated.

For `||`, if the left side is true, the right side may not be evaluated.

Example:
```c
if (ptr != NULL && *ptr == 10) {
    // safe check
}
```

## 13. Common Mistakes

Do not confuse:
```c
x = 5;   // assignment
x == 5;  // comparison
```

Do not confuse logical and bitwise operators:
```text
&&  → logical AND
&   → bitwise AND

||  → logical OR
|   → bitwise OR
```

## Quick Revision
```text
+ - * / %          → arithmetic
== != > < >= <=    → relational
&& || !            → logical
= += -= *= /= %=   → assignment
++ --              → increment/decrement
& | ^ ~ << >>      → bitwise
?:                 → ternary
sizeof             → size
```
