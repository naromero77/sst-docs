---
title: registerClock
---

```cpp
TimeConverter* registerClock(const std::string& freq, Clock::HandlerBase* handler, bool regAll = true);
TimeConverter* registerClock(const UnitAlgebra& freq, Clock::HandlerBase* handler, bool regAll = true);
TimeConverter* registerClock(const TimeConverter* freq, Clock::HandlerBase* handler, bool regAll = true);
```
*Availability:* Component, SubComponent, ComponentExtension

Register a clock at the specified frequency. On each clock cycle, the associated handler will be called. Unless otherwise specified, this call wil also sets the default time base for the (sub)component to match the clock frequency.


## Parameters
* **freq** (string, UnitAlgebra, TimeConverter*) Frequency of the clock
* **handler** (Clock::HandlerBase*) Clock handler function to invoke each cycle
* **regAll** (bool) Whether to set the (sub)component's default timebase to this clock frequency
* **returns** (TimeConverter*) A time converter representing the clock frequency


## Examples

<!--- SOURCE_CODE: sst-elements/src/sst/elements/simpleElementExample/example0.cc --->
### Example 1
```cpp
#include <sst/core/component.h>

example0::example0(ComponentId_t id, Params& params) : Component(id)
{
    /** Other configuration here */

    registerClock("1GHz", new Clock::Handler<example0>(this, &example0::clockTic));

    /** Other configuration here */
}
```

## Header
```cpp
#include <sst/core/component.h> // or
#include <sst/core/subcomponent.h> // or
#include <sst/core/componentExtension.h>
```
