---
title: unregisterClock
---

```cpp
void unregisterClock(TimeConverter* freq, Clock::HandlerBase* handler);
```
*Availability:* Component, SubComponent, ComponentExtension

Remove a clock. SST will no longer call the specified handler at the clock frequency specified by the time converter. Other clock handlers registered to the same time converter or other clocks registered with different time converters will be unaffected.


## Parameters
* **freq** (TimeConverter*) Frequency of the clock to unregister
* **handler** (Clock::HandlerBase*) Clock handler that should be unregistered
* **returns** (TimeConverter*) A time converter representing the clock frequency


## Examples

<!--- SOURCE_CODE: None --->
### Example 1
```cpp
#include <sst/core/component.h>
example::example(ComponentId_t id, Params& params) : Component(id) 
{
    /** Other configuration here */

    // Register a clock
    handler = new Clock::Handler<example>(this, &example::clockTick);
    clock_tc = registerClock("1GHz", handler);

    // Disable the clock for now
    unregisterClock(clock_tc, handler);
}
```

## Header
```cpp
#include <sst/core/component.h> // or
#include <sst/core/subcomponent.h> // or
#include <sst/core/componentExtension.h>
```
