---
title: It
permalink: /docs/it-construct/
---

<div class="alert alert-warning" role="alert">
  All assertions must be in an it block. Any assertions outside of an it block will run, but will not be included in the output summary.
</div>

It constructs contain the assertion for the current test scenario. They can be scoped to any construct.

---

#### it(char* description)

The it construct takes in the description of an assertion to reflect what is being tested.

---

#### Output

```
describe My Test Suite:
  context .add_two_ints
    it returns the sum of two numbers
    when the sum overflows
      it returns 0
        ...
```

---

### Example

<br />

```c
{% include examples/constructs/it/main.c %}
```