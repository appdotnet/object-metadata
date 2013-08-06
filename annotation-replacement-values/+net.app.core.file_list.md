# File List

<!-- specify the "key" for the replacement value -->
> ### +net.app.core.file_list

<!-- provide a description of the replacement value -->
This dynamically inserts information about a list of App.net [Files](http://developers.app.net/docs/resources/file/) into an annotation.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

### Provided to App.net
~~~ js
{
    "type": "com.example.test",
    "value": {
        "+net.app.core.file_list": [
            {
                "file_token": "12345abcde",
                "format": "url",
                "file_id": "1"
            },
            {
                "file_token": "98765zyx",
                "format": "url",
                "file_id": "1"
            }
        ],
        "other_values": "are preserved"
    }
}
~~~

### Returned by API
~~~ js
{
    "type": "com.example.test",
    "value": {
        "net.app.core.file_list": [
            {
                "file_token_read": "read file_token",
                "file_id": "1"
                "url": "http://example.com/file1.png",
                "url_expires": "2013-01-25T03:00:00Z"
            },
            {
                "file_token_read": "read file_token",
                "file_id": "2"
                "url": "http://example.com/file2.png",
                "url_expires": "2013-01-25T03:00:00Z"
            }
        ],
        "other_values": "are preserved"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

Each element in the `+net.app.core.file_list` list must match the format for [+net.app.core.file](https://github.com/appdotnet/object-metadata/blob/master/annotation-replacement-values/+net.app.core.file.md)

<!-- provide a way to contact you -->
## Maintainers
* App.net core team

<!-- provide references to compatible apps / service -->
## Used by
* [Omega](https://omega.app.net/)

<!-- provide references to related annotations -->
## Related annotations

* [+net.app.core.file](+net.app.core.file.md)
* [net.app.core.attachments](../annotations/net.app.core.attachments.md)
* [net.app.core.oembed](../annotations/net.app.core.oembed.md)
