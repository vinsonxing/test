## Attentions

#### Get attention
> Retrieve attention by type, if no such attention, just return a json object without message value, then GUI will ignore this attention.

> The values of name, message and action are all predefined, and support i18n.

> Fields:
> - action: should be mapped with corresponding GUI page for next action. According the value of this field, GUI will render a corresponding link to process this action.
> - message-data: values for the placeholders for field "message"

> Attention types:
> * Device that was attempted to be claimed is owned by someone else (day 0)
>     * Link to send request to claim or something like that (maybe a unplug it or something)
>     * Type Name: **wrong_claim_attempt**
>     * **Cloud API**
> * Internet is down
>     * Link to go to troubleshooting
>     * Type Name: **internet_down**
>     * **Cloud API**, send a request to cloud server for ping/pong to detect internet

* Method: GET
* URI: /api/v1/sites/{site-id}/attentions/{type}
* Response Body:

```json
{
    "type": "wrong_claim_attempt",
    "message": "message_key",
    "message-data": [],
    "timestamp": 1530512597135,
    "action": "action_type"
}
```

#### Ping pong

* Method: GET
* URI: /api/v1/sites/{site-id}/ping
* Response Body: N/A
* Response Code: 200 (if 200, it means internet works)
