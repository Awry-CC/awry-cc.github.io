---
title: Be True
permalink: /docs/assertions-be-true/
---

<div class="alert alert-danger" role="alert">
  This assertion does not use `stdbool.h` and applies an integer representation for booleans.
</div>

<div class="alert alert-warning" role="alert">
  Behavior is undefined in the context of an array.
</div>

The <span class="badge badge-info">be_true</span> assertion checks if the expected value equal to 1.

---

### Example

<br />

```c
{% include examples/assertions/betrue/main.c %}
```