---
title: After
permalink: /docs/fixtures-after/
---

After fixtures execute in a bottom-up pattern. The fixture at the lowest level of the suite will execute, then those in the current block execution hierarchy. 

After fixtures execute after each <span class="badge badge-info">it</span> block.

---

### Example

<br />

```c
{% include examples/fixtures/after/main.c %}
```