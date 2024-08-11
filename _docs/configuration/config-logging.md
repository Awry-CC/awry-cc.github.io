---
title: Logging
permalink: /docs/config-logging/
---

Awry logging offers DEVELOPMENT, FATAL. ERROR, WARN, INFO, and DEBUG logs. These logs offer insights into the internal state of Awry and its assertions. `Awry.log_level` is to be set prior to executing `Awry.run()`.

---

### Example

```c
AwryLogger.log_info("Block inserted into array buffer (%d/%d)", a->used, a->size);
```

---

#### log_level

**Default:** AWRY_LOG_NONE

**Options:** AWRY_LOG_NONE, AWRY_LOG_DEVELOPMENT, AWRY_LOG_FATAL, AWRY_LOG_ERROR, AWRY_LOG_WARN, AWRY_LOG_INFO, AWRY_LOG_DEBUG, AWRY_LOG_ALL 

Log output level from Awry.