<!-- give your annotation a title -->
### Broadcast Metadata

<!-- specify the "type" for your annotation -->
> ### net.app.core.broadcast.metadata

<!-- provide a description of what your annotation represents -->
The Broadcast Metadata annotation describes an App.net broadcast channel. This annotation can only be set on Channel objects with type `net.app.core.broadcast`. This annotation is informative and makes it possible for users to discover broadcast channels from the web and App.net apps.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "net.app.core.broadcast.metadata",
    "value": {
        "title": "@barmstrong's Broadcast Channel",
        "description": "Receive broadcasts about the latest @barmstrong updates",
        "tags": ["cool", "funny"]
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `title` | Required | string | The name of your Broadcast channel. This should be informative and must be no longer than 75 characters. |
| `description` | Required | string | This field describes what users can expect to see on your channel. This field can be as long as 1000 characters. |
| `tags` | Read-only | string | List of tags that help users find your channel. These are read-only and can only be set by the App.net team in order to prevent abuse. |

<!-- provide a way to contact you -->
## Maintainers
* App.net core team

<!-- provide references to compatible apps / service -->
## Used by

* App.net

<!-- provide references to related annotations -->
## Related annotations
* [net.app.core.broadcast.message.metadata](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.broadcast.message.metadata.md)
* [+net.app.core.broadcast.icon](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.broadcast.icon.md)
* [+net.app.core.broadcast.cover](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.broadcast.cover.md)
