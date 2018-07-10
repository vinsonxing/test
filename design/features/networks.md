# Network scenarios

## Add a new network
APIs:
- [POST /api/v1/networks](../api/tsn/networks.md#create-new-network) (T1)
- [POST /api/v1/sites/{site-id}/networks](../api/cloud/networks.md#create-new-network) (C1)

Workflow:
- Create new network on TSN and apply all configurations via T1
- Create new network record on cloud via C1

## Get a specific network
APIs:
- [GET /api/v1/sites/{site-id}/networks/{network-id}](../api/cloud/networks.md#get-a-specific-network)

Workflow:
- Show network detail on GUI

## Update a specific network
APIs:
- [PUT /api/v1/networks/{network-id}](../api/tsn/networks.md#apply-network-configuration-to-tsn) (T1)
- [PUT /api/v1/sites/{site-id}/networks](../api/cloud/networks.md#save-new-network) (C1)

Workflow:
- Apply network configurations to TSN first via T1
- Save updated network configuration to cloud via C1

## Remove a specific network
APIs:
- [DELETE /api/v1/sites/{site-id}/networks/{network-id}](../api/cloud/networks.md#delete-network) (C1)
- [DELETE /api/v1/networks/{network-id}](../api/cloud/networks.md#delete-network) (T1)

Workflow:
- Delete network by given id on cloud via C1
- Delete network by given id on TSN and remove all settings on TSN about this network
