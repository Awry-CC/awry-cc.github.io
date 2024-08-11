---
title: Overview
permalink: /docs/extensions-overview/
---

Awry can be extended to support custom data types. Awry uses C11's _Generic handle to identify the type for expect statements. You can add your own types by defining `AWRY_EXTENSIONS` before loading the Awry header.

---

### Scope

The comparison operations when defining expect extensions have access to the following variables:

- AwryModule *awry
  - Awry pointer

- (type / array) actual
  - Comparator value

- size_t actual_size
  - Size of the comparator

- int negated
  - Invert the function result

- (type / array) expected
  - Value of the expect() comparator

- size_t expected_size
  - Size of the expect() comparator

- (type) max_range
  - Max range value for in_range assertions

- size_t max_range_size
  - Max range size for in_range assertions

- awry_expect_flags flag
  - Assertion flag type (eg AWRY_EQUALS)

<br />

```c
void __expect_<function_identifier>(
  AwryModule *awry,
  type actual arr,
  size_t actual_size,
  int negated,
  type expected arr,
  size_t expected_size,
  type max_range arr,
  size_t max_range_size,
  Awry_expect_flags flag
);
```

---

### Notes

You must define a `__format_<function_identifier>(data_type value)` handler that returns the appropriate value associated with `printf_format` with expect extensions.

---

### Available Macros

<br />

#### AWRY_expect_forward(function_identifier, data_type)

Creates the forward definition of the expect function.

```c
AWRY_expect_forward(extstruct, ExpectExt*);
```

---

#### AWRY_expect_array_forward(function_identifier, data_type)

Creates the forward definition of the expect function for an array.

```c
AWRY_expect_array_forward(intarr, int);
```

---

#### AWRY_extension_forwards( VA_ARGS )

A list separated by a space or newline containing `AWRY_expect_forward` and `AWRY_expect_array_forward` definitions,

```c
AWRY_extension_forwards(
  AWRY_expect_forward(extstruct, ExpectExt*)
  AWRY_expect_array_forward(extstructarr, ExpectExt*)
)
```

---

#### AWRY_extension(function_identifier, data_type, comparison, printf_format)

Defines the expect function. Two variables are exposed in this context:

- data_type actual
- data_type expected

comparison can be any C expression or function call passing in the actual and expected variables.

printf_format is any printf format to display if the expectation fails. You can pass NULL if you do not want to print any error message.

