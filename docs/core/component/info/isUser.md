---
title: isUser
---
<!---
SAND202X-XXXX X
Source: location of source document if any
--->
```cpp
bool isUser();
```
*Availability:* Component, SubComponent, ComponentExtension

Returns whether the calling SubComponent was loaded as a User SubComponent (i.e., declared in the input configuration). This function always returns false for a Component.

## Parameters
* **returns** (bool) Whether the calling (Sub)Component was loaded as a User SubComponent


## Examples

<!--- SOURCE_CODE: None --->
### Example 1
```cpp
if (isUser()) {
    // Handle something one way if we were loaded as a user subcomponent
} else {
    // Handle a different way if we were loaded anonymously
}
```

## Header
```cpp
#include <sst/core/component.h> // or
#include <sst/core/subcomponent.h> // or
#include <sst/core/componentExtension.h>
```