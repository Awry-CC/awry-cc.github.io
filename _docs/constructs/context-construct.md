---
title: Context
permalink: /docs/context-construct/
---

Contexts wrap a set of tests against the functionality under a specific state. This can be a specific function or subject. 

---

#### context(char* context)

The <span class="badge badge-info">context</span> construct takes in the current context descriptor <span class="badge badge-info">char* context</span> and groups a set of tests in its output.

<br />

#### Output

```
describe My Test Suite:
  context .add_two_ints
    it returns the sum of two numbers
      ...
```

---

### Example

<br />

```c
{% include examples/constructs/context/main.c %}
```