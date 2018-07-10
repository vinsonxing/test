# Dashboard scenarios
> Describe each scenario from API invocations view.

## Show speed test diagram

APIs:
- [GET /api/v1/speed?duration=300](../api/tsn/speeds.md#get-speed) (T1)
- [GET /api/v1/sites/{site-id}/speeds](../api/cloud/speeds.md#get-speed-test-results) (C1)

> Hints: C1 for Cloud API call, T1 for TSN API call


Workflow:
- Calculate max upload and download speed from C1 as diagram's max value, use result in T1 as current value.
- If no valid results in C1, but T1 has, use T1's value as max value. It means the diagram render with 100% speed.
- If no valid result in both T1 and C1, current value is 0, max value is 1.

## Retrieve speed test history results
APIs:
- [GET /api/v1/sites/{site-id}/speeds](../api/cloud/speeds.md#get-speed-test-results)

Workflow:
- Show history results in a new page

## Launch speed test
APIs:
- [POST /api/v1/speed](../api/tsn/speeds.md#launch-speed-test) (T1)
- [GET /api/v1/speed/result](../api/tsn/speeds.md#get-a-current-running-speed-test-result) (T2)
- [POST /api/v1/sites/{site-id}/speeds](../api/cloud/speeds.md#save-speed-test-result) (C1)

Workflow:
- Invoke T1 to launch speed test on TSN
- Invoke T2 to retrieve current speed test status
- Once speed test is done, save current speed test result to cloud via C1

## Show network summary diagram
APIs:
- [GET /api/v1/sites/{site-id}/networks](../api/cloud/networks.md#get-network-list) (C1)
- [GET /api/v1/networks/{network-id}/allocated](../api/tsn/networks.md#get-network-allocated-count) (T1)

Workflow:
- Invoke C1 to retrieve network list
- Invoke T1 to retrieve current allocated client count

## Show device summary diagram
APIs
- [GET /api/v1/sites/{site-id}/devices/summary](../api/cloud/devices/devices.md#get-device-summaries) (C1)
- [GET /api/v1/devices/summary](../api/tsn/devices/devices.md#get-device-status) (T1)

Workflow:
- Invoke C1 to retrieve device list
- Invoke T1 to retrieve device realtime status
- Show merged info on GUI

## Show client summary diagram
APIs:
- [GET /api/v1/clients/summary](../api/tsn/clients.md#get-client-summaries) (T1)

Workflow:
- Show clients diagram according to T1

## Show security configuration list
APIs:
- [GET /api/v1/sites/{site-id}/securities/summary](../api/cloud/securoties.md#get-security-configuration-items) (C1)

Workflow:
- Show security configuration items according to C1 results
- If no results returned from C1, show default security setting

## Save a specific security configuration item
APIs:
- [PATCH /api/v1/securities/{name}](../api/tsn/securities.md#apply-security-item-to-tsn) (T1)
- [PATCH /api/v1/sites/{site-id}/securities/{name}](../api/cloud/securoties.md#save-security-item-to-cloud) (C1)

Workflow:
- Save security configuration item to TSN first.
- If Step 1 passed, save the security configuration item to cloud

## Show attention list
> Send several APIs call according to the attention type

APIs:
- [GET /api/v1/attentions/{type}](../api/tsn/attentions.md#get-attention)
- [GET /api/v1/sites/{site-id}/attentions/{type}](../api/cloud/attentions.md#get-attention)
- [GET /api/v1/sites/{site-id}/ping](../api/cloud/attentions.md#ping-pong)

Workflow:
- Retrieve attentions from TSN
- Retrieve attentions from cloud
- Retrieve attention from outside (such as version server)
- Consolidate all attention results and show on GUI
