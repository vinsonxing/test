# EZ1K API definitions

> There are two parts API for For EZ1k Mobile App, TSN and cloud. APIs for cloud are used to manage static data, and APIs for TSN are used to manage  dynamical data. In most cases, the data on Mobile App comes from both of two parts.

## Shared error response format
> i18n supported

> Fields:
> * error-code: key is mapped to a translatable string, which can include placeholders (variables from backend)
> * error-message: default English error message from backend
> * error-data: variables used in error message

Response Body:

```json
{
  "error-code": "",
  "error-message": "",
  "message-data": [""]
}
```
Response Code: Per error

APIs:

- [Sites](./sites.md#### Get a specific site)
- [Sites](./sites.md#Get a specific site)
> All sites related apis go here. All APIs in it need not add HTTP header X-EZ1K-SITE-ID, since they cross sites.

- [Dashboard](./dashboard.md)
> All about dashboard scenarios

- [Device](./devices.md)
> All about device management

- [Network](./networks.md)
> All about network management
