---
title: Definitions
permalink: /docs/config-definitions/
---

The following macros are to be defined before loading `awry.h`. These macros allow changes in the behavior of Awry.

---

#### AWRY_MAX_ASSERTION_BUFFER

**Default:** 0x400

The assertion text output buffer. Redefine if your codebase has long structure or function names, or string-based return values.

---

#### AWRY_EXPECT_EPSILON

**Default:** 0.000001

Assertion precision for floating-point values. Redefine if more precise measurement is needed.
