---
title: Overview
permalink: /docs/home/
redirect_from: /docs/index.html
---

<style>
  ul.badges { list-style-type: none; margin: 0; padding: 0; margin-bottom: 1em; }
  ul.badges li { display: inline-block; }
</style>

<ul class="badges">
  <li><img src="https://github.com/Awry-CC/awry/actions/workflows/MacOS.yml/badge.svg"/></li>
  <li><img src="https://github.com/Awry-CC/awry/actions/workflows/Windows.yml/badge.svg"/></li>
  <li><img src="https://github.com/Awry-CC/awry/actions/workflows/Ubuntu.yml/badge.svg"/></li>
</ul>

---

## Goals

<br />

- A small, behavior-driven, test library for C.
- No extensions to the C-library
- Extensible assertions

---

## Functionality

<br />

- An elegant syntax
- A variety of default assertions
- Signal Capturing
- Extensible
- Configurable Output Formats

---

## Example

<br />

```c
#include "awry/awry.h"

describe("Awry", awry_suite)
  it("is defined")
    expect(&Awry) to equal(&Awry)
  end
  
  context(".register_block")
    when("a block has not had any it blocks defined")
      it("creates a new array with 1 element")
        Awry.register_block(IT_TYPE, &Awry, "it block test");
        expect(Awry.current->it_blocks.size) to equal(1);
      end
    end
  end
end

int main() {
  Awry.run();
  int failures = Awry.failures;
  Awry.clear(&Awry); // optional, frees memory and clears the test suite
  return failures > 0 ? 1 : 0;
}
```

### Output

```
describe Awry:
  ✔ it is defined
  context .register_block
    when a block has not had any it blocks defined
      ✔ it creates a new array with 1 element
```
