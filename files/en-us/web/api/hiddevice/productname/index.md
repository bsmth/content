---
title: "HIDDevice: productName property"
short-title: productName
slug: Web/API/HIDDevice/productName
page-type: web-api-instance-property
status:
  - experimental
browser-compat: api.HIDDevice.productName
sidebar:
  - apiref:
      - WebHID API")}}{{SeeCompatTable}}{{AvailableInWorkers("window_and_worker_except_shared
---

{{securecontext_header}}

The **`productName`** read-only property of the {{domxref("HIDDevice")}} interface returns the product name of the connected HID device.

## Value

A string.

## Examples

The following example retrieves devices with {{domxref("HID.getDevices()")}} and logs the value of `productName` to the console.

```js
document.addEventListener("DOMContentLoaded", async () => {
  let devices = await navigator.hid.getDevices();
  devices.forEach((device) => {
    console.log(`HID: ${device.productName}`);
  });
});
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
