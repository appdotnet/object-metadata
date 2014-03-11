<!-- give your annotation a title -->
### Broadcast Metadata

<!-- specify the "type" for your annotation -->
> ### net.app.core.channel.metadata

<!-- provide a description of what your annotation represents -->
The Channel Metadata annotation describes an App.net channel. This annotation is very similar to the [App.net Broadcast Metadata annotation](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.broadcast.metadata.md) but is meant to be used for non-Broadcast channels. This annotation can not be set on Channel objects with type `net.app.core.broadcast`. App.net indexes this annotation for [Channel Search](https://developers.app.net/docs/resources/channel/search/).

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "net.app.core.channel.metadata",
    "value": {
        "title": "@barmstrong's really cool channel",
        "description": "Messages from @barmstrong",
        "tags": ["cool", "funny"]
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `title` | Required | string | A name describing your channel. This should be informative and must be no longer than 75 characters. |
| `description` | Required | string | This field describes what users can expect to see on your channel. This field can be as long as 1000 characters. |
| `tags` | Optional | list of strings | List of tags that help users find your channel. Each tag can be at most 15 characters and each channel can have at most 3 tags. |

<!-- provide a way to contact you -->
## Maintainers
* App.net core team

<!-- provide references to compatible apps / service -->
## Used by

* App.net search

<!-- provide references to related annotations -->
## Related annotations
* [net.app.core.broadcast.metadata](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.broadcast.metadata.md)
