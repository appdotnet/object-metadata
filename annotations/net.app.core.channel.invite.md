<!-- give your annotation a title -->
# Channel Invite

<!-- specify the "type" for your annotation -->
> ### net.app.core.channel.invite

<!-- provide a description of what your annotation represents -->
The channel invite annotation can be used to indicate that a [Post](http://developers.app.net/docs/resources/post/) is an invitation to join in a conversation taking place in a [Channel](http://developers.app.net/docs/resources/channel/). Posts using this annotation should likely use the [fallback url annotation](net.app.core.fallback_url.md) as well to indicate a place where the channel can be viewed if the current client cannot properly render the channel type.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "net.app.core.channel.invite",
    "value": {
        "channel_id": "1234",
        "channel_type": "com.example.channel"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field          | Required? | Type   | Description                                                                        |
| -----          | --------- | ----   | -----------                                                                        |
| `channel_id`   | Required  | string | A [Channel](http://developers.app.net/docs/resources/channel/) id.                 |
| `channel_type` | Required  | string | A [Channel type](http://developers.app.net/docs/resources/channel/#channel-types). |

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to related annotations -->
## Related annotations
* [Fallback URL](net.app.core.fallback_url.md)

<!-- provide references to compatible apps / service -->
## Used by
