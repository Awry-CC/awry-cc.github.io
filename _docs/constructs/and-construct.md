---
title: And
permalink: /docs/and-construct/
---

And constructs expand the current testing scenario, groups tests that assert the conditions.

---

#### and(char* condition)

The <span class="badge badge-info">and</span> construct takes in the condition descriptor <span class="badge badge-info">char* condition</span> and groups a set of tests in its output.

<br />

#### Output

```
describe My Test Suite:
  context .add_two_ints
    when the sum does not overflow
      and both number are not negative
        it returns the sum of two numbers
        ...
```

---

### Example

<br />

```c
{% include examples/constructs/and/main.c %}
```