---
title: Before
permalink: /docs/fixtures-before/
---

Before fixtures execute in a top-down pattern. The fixture at the highest level of the suite will execute, then those in the current block chain.

Before fixtures execute before each <span class="badge badge-info">it</span> block.

---

### Example

<br />

```c
{% include examples/fixtures/before/main.c %}
```