# File

<!-- specify the "key" for the replacement value -->
> ### +net.app.core.file

<!-- provide a description of the replacement value -->
This dynamically inserts information about an App.net file into an annotation. The File information is merged with any other values to form a single object.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

### `url` format

#### Provided to App.net
~~~ js
{
    "type": "com.example.test",
    "value": {
        "+net.app.core.file": {
            "file_token": "12345abcde",
            "format": "url",
            "file_id": "1",
        },
        "other_values": "are preserved"
    }
}
~~~

#### Returned by API
~~~ js
{
    "type": "com.example.test",
    "value": {
        "file_token": "new_file_token",
        "file_id": "1",
        "url": "http://example.com/file_url.png"
        "other_values": "are preserved"
    }
}
~~~


### `metadata` format

#### Provided to App.net

~~~ js
{
    "type": "com.example.test", # also works with the net.app.core.oembed annotation
    "value": {
        "+net.app.core.file": {
            "file_token": "12345abcde",
            "format": "metadata",
            "file_id": "1",
        },
        "other_values": "are preserved"
    }
}
~~~

#### Returned by API

~~~ js
{
    "type": "com.example.test",
    "value": {
        "file_token": "new_file_token",
        "file_id": "1",
        "complete": true,
        "mime_type": "image/png"
        ...other File object values...
        "other_values": "are preserved"
    }
}
~~~


### `oembed` format

#### Provided to App.net

~~~ js
{
    "type": "com.example.test", # also works with the net.app.core.oembed annotation
    "value": {
        "+net.app.core.file": {
            "file_token": "12345abcde",
            "format": "oembed",
            "file_id": "1",
        },
        "other_values": "are preserved"
    }
}
~~~

#### Returned by API

~~~ js
{
    "type": "com.example.test",
    "value": {
        "file_token": "new_file_token",
        "file_id": "1",
        "version": "1.0",
        "type": "photo",
        ...other oembed values...
        "other_values": "are preserved"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `file_token` | Required | string | A valid file token that App.net returned when you uploaded a file.|
| `format` | Required | string | Either `metadata`, `oembed`, or `url` depending on what data you want provided for this file. |
| `file_id` | Required | string | The id of the file. |

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to compatible apps / service -->
## Used by

<!-- provide references to related annotations -->
## Related annotations

* [net.app.core.attachments](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.attachments.md)
* [net.app.core.oembed](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.oembed.md)
* [+net.app.core.file_list](https://github.com/appdotnet/object-metadata/blob/master/annotation-replacement-values/+net.app.core.file_list.md)