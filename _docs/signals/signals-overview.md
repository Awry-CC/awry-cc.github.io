---
title: Overview
permalink: /docs/signals-overview/
---

Awry can be configured to capture signals in assertion (`it`) blocks. SIGABRT, SIGFPE, SIGILL, SIGINT, SIGSEGV, SIGTERM are supported. To capture a signal, or multiple signals, `Awry.signals` is to be set prior to `Awry.run`. To add multiple signals, chain a bitwise `or` for each signal.

Each signal is prefixed with `AWRY_` for chaining. Example: `AWRY_SIGFPE`, `AWRY_SIGSEGV`, etc. When a signal is captured, Awry will report the error in the test suite with the signal number and continue execution.

---

#### Example

<br />

```c
AWRY.signals = AWRY_SIGFPE | AWRY_SIGSEGV;
AWRY.run();
```

##### Result

```
 describe  AWRY:
    context  Signals
      when  a signal is captured
        ✖ it reports the error 
        Expected (Signal) to not have been captured (11) 
      when  the signal was captured
        ✔ it runs the next test 
```