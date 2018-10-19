---
title: Ternary Operator
---

## Ternary Operator

Programmers use ternary operators in C for decision making inplace of conditional statements **if** and **else**.
The ternary operator is an operator that takes three arguments. The first argument is a comparison argument, the second is the result upon a true comparison, and the third is the result upon a false comparison. If it helps you can think of the operator as shortened way of writing an if-else statement.

Here's a simple decision-making example using **if** and **else**:

```c
int a = 10, b = 20, c;

if (a < b) {
    c = a;
}
else {
    c = b;
}

printf("%d", c);
```

This example takes more than 10 lines, but that isn't necessary. You can write the above program in just 3 lines of code using the **ternary operator**.

### Syntax

`condition ? value_if_true : value_if_false`

The statement evalutes to statement\_1 if the condition is true, and statement\_2 otherwise.

Here's the above example re-written to use the ternary operator:

```c
int a = 10, b = 20, c;

c = (a < b) ? a : b;

printf("%d", c);
```

Output of the example should be:

```c
10
```

`c` is set equal to `a`, because the condition `a<b` was true.

This looks pretty simple, right? Do note that `value_if_true` and `value_if_false` must have the same type, and they cannot be full statements but simply expressions.

The ternary operator can be nested too same like nested if-else statements. Consider this nested if-else statement :
```c
int a = 1, b = 2, ans;
if (a == 1) {
    if (b == 2) {
        ans = 3;
    } else {
        ans = 5;
    }
} else {
    ans = 0;
}
printf ("%d\n", ans);
```

Here's the above code re-written using nested ternary operator:

```c
int a = 1, b = 2, ans;
ans = (a == 1 ? (b == 2 ? 3 : 5) : 0);
printf ("%d\n", ans);
```

The output of both of the above codes should be:

```c
3
```

#Addition of the Elvis Operator in GNU C.
In C and C++ with GCC extensions, the second operand of the ternary operator is optional. 
This has been the case since at least GCC 2.95.3
The middle operand in a conditional expression may be omitted. 
Then if the first operand is nonzero, its value is the value of the conditional expression.
This ternary operator is specially called the Elvis operator.
The following expression:

```c
x ? : y
```

has the value of x if that is nonzero; otherwise, the value of y. 
The above expression gives the same result as

```c
x ? x : y
```

While in this simple case it may not be essentially useful to omit the middle operand, there are situations where becomes useful, when the first operand does, or may (if it is a macro argument), contain some side effect. 
This implies that repeating the operand would have the side effect performed twice. 
Omission of the middle operand uses the value already computed without the undesirable effects of recomputing it. 
