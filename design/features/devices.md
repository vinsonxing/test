# Switch scenarios

## Show switch list
APIs:
- [GET /api/v1/devices/summary](../api/tsn/devices/devices.md#get-device-status) (T1)

Workflow:
- Show switch list from T1 results


## Show switch detail
APIs:
- [GET /api/v1/sites/{site-id}/switches/{switch-id}](../api/cloud/devices/switches.md#get-switch-detail) (C1)
- [GET /api/v1/networks/{network-id}/allocated](../api/tsn/networks.md#get-Network-allocated-count) (T1)
- [GET /api/v1/switches/{switch-id}](../api/tsn/devices/switches.md#get-switch-detail) (T2)

Workflow:
- Invoke C1 to retrieve static info of switch
- Invoke T1 to get connected clients
- Invoke T2 to get operational switch status
- Merge result and show on GUI
