<!-- give your annotation a title -->
# Fallback URL

<!-- specify the "type" for your annotation -->
> ### net.app.core.fallback_url

<!-- provide a description of what your annotation represents -->
The fallback URL annotation is meant to specify a URL that can properly display a resource, should the current consumer not be able to. 

One use case for this annotation is as a [Channel](http://developers.app.net/docs/resources/channel/) annotation, where a client can fall back to the specified URL after inspecting a Channel's type and determining it does not know how to render a Channel of that type.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "net.app.core.fallback_url",
    "value": {
        "url": "http://example.com/channelviewer?id=1234"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type   | Description                                                           |
| ----- | --------- | ----   | -----------                                                           |
| `url` | Required  | string | A URL that will properly render the object utilizing this annotation. |

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to related annotations -->
## Related annotations
* [Channel Invite](net.app.core.channel.invite.md)

<!-- provide references to compatible apps / service -->
## Used by
