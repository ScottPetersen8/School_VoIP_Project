# File: extensions.conf

## Purpose
Defines the dial plan logic for internal calls.

## Key Sections
- `[general]`: Global settings
- `[default]`: Default context
- `[from-internal]`: Internal call routing

  # Internal Dial Plan Logic

## Extensions
- 1001 – Test1
- 1002 – Test2
- 1003 - Test3


## Ring Groups
- 200 – All Staff Phones

## Voicemail 
- Enabled for all extensions
- Voicemail timeout: 15 seconds
  - Connectivity - Extensions - (select extension) - Advanced - Extension Options - Ring Time
    
## Call Forwarding
- 1001 forwards to 1002 if busy
   - Connectivity - Extensions - (select extension) - Find Me/Follow Me - (Enable) - Follow-Me List (selects who is called after the initail ring time)

## Feature Codes
- *97 – Voicemail
- *80 – Intercom


## Example
```ini
[from-internal]
exten => 1001,1,Dial(SIP/1001)
exten => 1002,1,Dial(SIP/1002)
```
