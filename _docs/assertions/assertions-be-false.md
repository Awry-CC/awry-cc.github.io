---
title: Be False
permalink: /docs/assertions-be-false/
---

<div class="alert alert-danger" role="alert">
  This assertion does not use `stdbool.h` and applies an integer representation for booleans.
</div>

<div class="alert alert-warning" role="alert">
  Behavior is undefined in the context of an array.
</div>

The <span class="badge badge-info">be_false</span> assertion checks if the expected value is equal to 0.

---

### Example

<br />

```c
{% include examples/assertions/befalse/main.c %}
```