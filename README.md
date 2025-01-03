# -0_common

The real common library, even for header-only libraries.

## Features

1. Type `g_err_t` is defined as `bool` and indicates there's an error if `true`.
2. Macro `G_API` indicates that it's public.

## Prerequisites

To use any `-n` libraries, you need to define `G_SHARED` to `0` or `1`:

- `0` if the libraries will be used as a static library.
- `1` if the libraries will be used as a shared library.

This is to correctly apply `__declspec(...)` for Windows.

## Usage for Using the Library

Define `G_SHARED` as `1` if the library is shared, or `0` otherwise.

## Usage for Creating the Library

Source code implementing the library should follow these steps:

1. Define `G_EXPORT` **only** in the header file.
2. After including other libraries, include `-0/common_export.h`.
3. Use `G_API` with every public symbol.

```c
#define G_EXPORT
#include "HEADER_INCLUDING_FUNCTION_DECLARATION.h"
#undef G_EXPORT

#include "other.h"
#include "libraries.h"

#include "-0/common_export.h"

// Function definitions
G_API int ft(void);
```
