---
title: Example
permalink: /docs/extensions-example/
---

Assertion extensions are broken up into forwards, expectation setup, assertion definition, and output format.

---

### testsuite.h

<br />

```c
{% include examples/extensions/custom_format/testsuite.h %}
```

<br />

#### Forwards

Forwards are defined in the header for defining `AWRY_extension_forwards`. The `AWRY_extension_forwards` macro is inserted into the `_Generic` expectation call function if defined. 

---

#### Expectation Setup

After defining forwards, the `AWRY_EXTENSIONS` macro in your header file is to be defined with `AWRY_setup_extensions`, space or newline delimited list containing `AWRY_extension` definitions matching the forwards.

---

#### extension.c

Assertion definitions are created by the `AWRY_expect_extension`,, `AWRY_expect_extension_default`, and `AWRY_expect_array_extension_default` macros. Any post-fixed macros with `default` must take `NULL` as the printf format to create a generic error message handler. Assertions can be a function call or C expression.

```c
{% include examples/extensions/custom_format/extension.c %}
```

---

#### Output Format

Output formats, excluding those post fixed with `default` are to return a value associated with the printf expression.

---

### Full Example

**testsuite.h**

```c
{% include examples/extensions/custom_format/testsuite.h %}
```

**extension.c**

```c
{% include examples/extensions/custom_format/extension.c %}
```

**main.c**

```c
{% include examples/extensions/custom_format/main.c %}
```