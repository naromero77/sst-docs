---
id: setProgramOption
title: setProgramOption
---

<!---
SAND2022-6843 O
Source: sst-documentation/manuals/python
--->
Sets the specified program option for the simulation. These mirror the options available on the sst command line. Parameters set in the python file will be overwritten by options set on the command line. Use sst –help to get a list of available options. 

## Syntax
```python
sst.setProgramOption(option, value)
```

## Parameters
* **option** (type: string) configuration option to set 
* **value** (type: varies by option) value to set option to 
* **returns** none

## Examples

### Example 1
```python
import sst

sst.setProgramOption("exit-after", "100ms")
```

## Import
```python
import sst
```