---
title: In Range
permalink: /docs/assertions-inrange/
---

<div class="alert alert-warning" role="alert">
  Behavior is undefined in the context of an array.
</div>

The <span class="badge badge-info">in_range</span> assertion checks if the expected numeric value is greater than or equal to the lower bound, and less than or equal to the upper bound.

---

### Example

<br />

```c
{% include examples/assertions/inrange/main.c %}
```