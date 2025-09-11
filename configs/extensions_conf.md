# File: extensions.conf

## Purpose
Defines the dial plan logic for internal and external calls.

## Key Sections
- `[general]`: Global settings
- `[default]`: Default context
- `[from-internal]`: Internal call routing

## Example
```ini
[from-internal]
exten => 1001,1,Dial(SIP/1001)
exten => 1002,1,Dial(SIP/1002)
```
