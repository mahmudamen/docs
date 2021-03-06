---
title: 'battery'
notes:
  - 'Needs example, spec reference'
readiness: 'In Progress'
relationships:
  applies_to:
    predicate: 'Property of '
    value: apis/battery_status/NavigatorBattery
    href: /apis/battery_status/NavigatorBattery
  return:
    predicate: 'Returns an object of type '
    value: BatteryManager
    href: /apis/battery_status/NavigatorBattery
standardization_status: 'W3C Candidate Recommendation'
summary: 'The object that exposes the battery status information.'
tags:
  - API_Object_Properties
  - API
  - Battery_Status
  - Mobile
  - Needs_Examples
uri: 'apis/battery status/NavigatorBattery/battery'

---
## Summary

The object that exposes the battery status information.

Property of [apis/battery\_status/NavigatorBattery](/apis/battery_status/NavigatorBattery)[apis/battery\_status/NavigatorBattery](/apis/battery_status/NavigatorBattery)

## Syntax

**Note**: This property is read-only.

``` js
var result = navigator.battery;
```

## Return Value

Returns an object of type BatteryManagerBatteryManager

