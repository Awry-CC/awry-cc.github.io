---
title: Overview
permalink: /docs/fixtures-overview/
---

Fixtures set up and clear state for each of your test cases. Fixture functions can run before each <span class="badge badge-info">it</span> block, or after.

Fixtures are void functions that accept a pointer to a pointer <span class="badge badge-info">**subject</span> parameter.

```c
void fixture_name(void **subject);
```

---

### subject()

The <span class="badge badge-info">subject()</span> macro retrieves the current <span class="badge badge-info">**subject</span> state. The result of this macro can be implicitly cast to your subject type.

```c
Person *state = subject();
```

---

### define_fixture(macro before|after, function_name)

The <span class="badge badge-info">define_fixture</span> macro constructs the function handle for the context in which it's registered.

```c
define_fixture(before, before_all) {
  puts("Run before all tests");
}

define_fixture(before, after_all) {
  puts("Run after all tests");
}
```

---

### set_fixture(macro before|after, function_name)

Registers the fixture to run in the current block and and child blocks.

```c
set_fixture(before, before_all)
```

### Example

<br />

```c
{% include examples/fixtures/complete/main.c %}
```