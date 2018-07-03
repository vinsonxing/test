# EZ1K API definitions

> Multiple sites are supported in EZ1K mobile app, so we add a HTTP header to indicate the current site. The header name is X-EZ1K-SITE-ID. Then all the API URIs site oriented are needless to carry site info.

>X-EZ1K-SITE-ID="ID"

## Shared error response format
> i18n supported

> Fields:
* error-code: key is mapped to a translatable string, which can include placeholders (variables from backend)
* error-message: default English error message from backend
* error-data: variables used in error message

Response Body:

```json
{
  "error-code": "",
  "error-message": "",
  "error-data": [""]
}
```
Response Code: Per error

APIs:

- [Sites](./sites.md)
> All sites related apis go here. All APIs in it need not add HTTP header X-EZ1K-SITE-ID, since they cross sites.

- [Networks](./networks.md)

- [Devices](./devices.md)

- [Dashboard](./dashboard.md)
> All dashboard apis go here. As dashboard APIs are all about summary of each API Object, We prefer to separate APIs from feature perspective for it.
