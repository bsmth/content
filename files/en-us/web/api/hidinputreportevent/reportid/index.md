---
title: "HIDInputReportEvent: reportId property"
short-title: reportId
slug: Web/API/HIDInputReportEvent/reportId
page-type: web-api-instance-property
status:
  - experimental
browser-compat: api.HIDInputReportEvent.reportId
---

{{securecontext_header}}{{APIRef("WebHID API")}}{{SeeCompatTable}}{{AvailableInWorkers("window_and_worker_except_shared")}}

The **`reportId`** property of the {{domxref("HIDInputReportEvent")}} interface returns the one-byte identification prefix for this report, or 0 if the HID interface does not use report IDs.

## Value

A one-byte identification prefix.

## Examples

In the following example the `reportId` of an incoming input report is logged to the console.

```js
device.addEventListener("inputreport", (event) => {
  const { data, device, reportId } = event;
  console.log(reportId);
});
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
