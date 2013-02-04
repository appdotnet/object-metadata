<!-- give your annotation a title -->
# Attachments

<!-- specify the "type" for your annotation -->
> ### net.app.core.attachments

<!-- provide a description of what your annotation represents -->
Attach App.net [Files](http://developers.app.net/docs/resources/file/) to this resource.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

### Provided to App.net
~~~ js
{
    "type": "net.app.core.attachments",
    "value": {
        "+net.app.core.file_list": [
            {
                "file_token": "12345abcde",
                "format": "metadata",
                "file_id": "1"
            }
        ]
    }
}
~~~

### Returned by API

~~~ js
{
    "type": "net.app.core.attachments",
    "value": {
        "+net.app.core.file_list": [
            {
                "file_token_read": "new_file_token",
                "file_id": "1",
                "complete": true,
                "mime_type": "image/png"
                ...other File object values...
            }
        ]
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `+net.app.core.file_list` | Required | list | A list that matches the [+net.app.core.file_list](../annotation-replacement-values/+net.app.core.file_list.md) validations. For this annotation, the only `format` allowed is `metadata`|

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to compatible apps / service -->
## Used by

<!-- provide references to related annotations -->
## Related annotations
* [+net.app.core.file](../annotation-replacement-values/+net.app.core.file.md)
* [+net.app.core.file_list](../annotation-replacement-values/+net.app.core.file_list.md)
* [net.app.core.oembed](net.app.core.oembed.md)
