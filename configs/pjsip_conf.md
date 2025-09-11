# File: pjsip.conf

## Purpose
Defines SIP endpoints using the PJSIP channel driver.

## Key Sections
- `[global]`: Global SIP settings
- `[endpoint]`: Device definitions
- `[auth]`: Authentication settings

## Example
```ini
[1001]
type=endpoint
context=from-internal
transport=udp
```
