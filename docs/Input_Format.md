# Model Input Guide

## Input file format

```
max +2 +3 +3 +5 +2 +4
+11 +8 +6 +14 +10 +10 <=40
bin bin bin bin bin bin
```

- Line 1: `max` or `min`, then a signed objective coefficient per decision variable.
- Then one line per constraint: signed technological coefficients, the relation (`<=`, `>=`, `=`) and the RHS.
- Last line: one sign restriction per variable — `+`, `-`, `urs`, `int`, `bin`.

Any number of variables and constraints is accepted. `#` and `//` start a comment.

### Non-linear input format (bonus criterion)

A non-linear model is written a different, shorter way — a function of one variable and the interval
to search it over:

```
max 4sin(x)(1 + cos(x))
0 <= x <= 1.5707963268
tolerance 0.05
```

Line 3 is optional and defaults to `0.001`. You may write `+ - * / ^`, brackets, the functions
`sin cos tan sqrt exp ln log abs` and the constants `pi` and `e`. Multiplication may be left implicit,
so `4sin(x)(1 + cos(x))` and even the notes' `4sinx(1 + cosx)` both parse.

The program tells the two formats apart on its own: a linear objective line is nothing but signed
numbers, so a letter on that line means the file is non-linear.

