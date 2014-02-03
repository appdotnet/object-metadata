<!-- give your annotation a title -->
### Broadcast Icon

<!-- specify the "type" for your annotation -->
> ### net.app.core.broadcast.icon

<!-- provide a description of what your annotation represents -->
The Broadcast Icon is a `+net.app.core.file` image attachment. This icon is rendered for each Broadcast Channel on the App.net Broadcast directory on the web and in the app. This image must be square and at least 200x200 pixels.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

### Provided to App.net
~~~ js
{
    "type": "net.app.core.broadcast.icon",
    "value": {
        "+net.app.core.file": {
            "file_token": "12345abcde",
            "format": "metadata",
            "file_id": "1"
        }
    }
}
~~~

### Returned by API

~~~ js
{
    "type": "net.app.core.broadcast.icon",
    "value": {
        "complete": true,
        "created_at": "2013-11-12T18:00:00Z",
        "file_id": "1",
        "file_token_read": "12345abcde",
        "image_info": {
            "height": 200,
            "width": 200
        },
        "kind": "image",
        "mime_type": "image/png",
        "name": "example.png",
        "public": false,
        "sha1": "12345678",
        "size": 10000,
        "total_size": 10000,
        "type": "net.app.alpha.attachment",
        "url": "https://temporary-file-url.not.a.real.domain",
        "url_expires": "2013-11-12T20:00:00Z"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `+net.app.core.file` | Required | object | An object that matches the [+net.app.core.file](../annotation-replacement-values/+net.app.core.file.md) validations. For this annotation, the only `format` allowed is `metadata`, and the file must be a square image measuring at least 200x200 pixels.|

<!-- provide a way to contact you -->
## Maintainers
* App.net core team

<!-- provide references to compatible apps / service -->
## Used by

* App.net

<!-- provide references to related annotations -->
## Related annotations
* [net.app.core.broadcast.metadata](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.broadcast.metadata.md)
