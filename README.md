# RockÉTS coding style

This file and repo dictates the coding style to use when contributing C code on Club RockÉTS repositories.

## General

### Identation

Code should be idented with 4 spaces.

### Trailing whitespace

Code should not contain trailing whitespace but source files should end with a newline.

### Braces

Braces should never be dropped, and should be placed on the same line as the condition, except for function names (K&R style).

```c
// Good
int main()
{
    if (condition) {
        something();
    }

    do {
        // Stuff
    } while (true);
}
```

```c
// Bad
void java() {
    if (condition)
        something();

    do
    {
        // Stuff
    }
    while (true);
}
```

### Pointer alignement

Both pointer types and reference types should be written with no space between the type name and the \*, except when multiple pointers are declared on the same line;

```c
// Good
int* a;
float *b, *c;

// Bad
int *a;
float* b,* c;
```

### Complex Macros

Macros composed of more than one line should be wrapped in a `do { ... } while (0)` block.

```c
#define DO_SOMETHING(param1, param2) \
    do {\
        function_alpha(param1);\
        function_bravo(param2);\
    } while (0)
```

### Header guards

All header files should contain an header guard. The header guard define should be the file name in ALL_CAPS, with the `.` substituded for an `_`, and a trailing `_` added.

```c
#ifndef KARMAN_FILTER_H_
#define KARMAN_FILTER_H_
// karman_filter.h

#endif
```

## Naming

### Files

File should be named in snake_case.

### Functions

Functions should be in snake_case. They should be prefixed with the module name.

```c
// Good
int mti_set_config();
void karman_filter_data(int len, int *data);

// Bad
void PowerGet();
void doSomethingElse(int parameter);
```

### Macros

Macros should be in ALL_CAPS.

```c
#define PI 3.141592
#define DO_SOMETHING(param) do { something(param); } while (0)
```

### Variables

Constant variables should be in ALL_CAPS. File and function scope variables should be named in snake_case.

```c
const int SPEED_OF_LIGHT = 299792468;

int function()
{
    int param;
    float pi = 3.141592f;
}
```