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

Features:

- [Dashboard](./features/dashboard.md)
> All about dashboard scenarios

- [Device](./features/devices.md)
> All about device management

- [Network](./features/networks.md)
> All about network management
