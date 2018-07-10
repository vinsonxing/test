## Attentions

#### Get attention
> Retrieve attention by type, if no such attention, just return a json object without message value, then GUI will ignore this attention.

> The values of name, message and action are all predefined, and support i18n.

> Fields:
> - action: should be mapped with corresponding GUI page for next action. According the value of this field, GUI will render a corresponding link to process this action.
> - message-data: values for the placeholders for field "message"

> Attention types:
> * Discovered new switches or AP to claim
>     * Link to claim these devices
>     * Type Name: **new_device_discovered**
>     * **TSN API**
> * Switch/AP is down
>     * Link to troubleshooting
>     * Type Name: **device_down**
>     * **TSN API**
> * DHCP pool is getting full  
>     * Link to config
>     * Type Name: **dhcp_full**
>     * **TSN API**
> * Software images (Route/Switch/Wireless) is available
>     * Link to upgrade
>     * Type Name: **image_available***
>     * **Mobile Behavior**, send request to version server
> * IPSec is down (if enabled)  
>     * Link to troubleshoot or configure
>     * Type Name: **ipsec_down**
>     * **TSN API**
> * Device HW fault detected  
>     * Link to troubleshoot or device page
>     * Type Name: **hardware_fault**
>     * **TSN API**
> * AP Mesh link is too weak  
>     * Link to troubleshoot or device page (hard one)
>     * Type Name: **weak_mesh**
>     * **TSN API**
> * Radius is failing
>     * Link to troubleshoot application (hard one)
>     * Type Name: **radius_fail**
>     * **TSN API**
> * POE over budget for switches and router (link to device page)
>     * Type Name: **poe_over_budget**
>     * **TSN API**

* Method: GET
* URI: /api/v1/attentions/{type}
* Response Body:

```json
{
    "type": "new_device_discovered",
    "message": "message_key",
    "message-data": [],
    "timestamp": 1530512597135,
    "action": "action_type"
}
```
