<!-- give your annotation a title -->
### Broadcast Message Metadata

<!-- specify the "type" for your annotation -->
> ### net.app.core.broadcast.message.metadata

<!-- provide a description of what your annotation represents -->
This annotation provides a place to attach a subject to your Broadcast message. This subject appears when the message is pushed to subscribers in the App.net app.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "net.app.core.broadcast.message.metadata",
    "value": {
        "subject": "Check out this awesome thing that just happened"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `subject` | Required | string | The subject of your Broadcast message. Must be no more than 128 characters.

<!-- provide a way to contact you -->
## Maintainers
* App.net core team

<!-- provide references to compatible apps / service -->
## Used by

* App.net

<!-- provide references to related annotations -->
## Related annotations
* [net.app.core.broadcast.metadata](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.broadcast.metadata.md)
