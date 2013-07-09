# File

<!-- specify the "key" for the replacement value -->
> ### +net.app.core.file

<!-- provide a description of the replacement value -->
This dynamically inserts information about an App.net [File](http://developers.app.net/docs/resources/file/) into an annotation. The File information is merged with any other values to form a single object.

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
        "file_token_read": "new_file_token",
        "file_id": "1",
        "url": "http://example.com/file_url.png",
        "url_expires": "2013-01-25T03:00:00Z",
        "other_values": "are preserved"
    }
}
~~~


### `metadata` format

#### Provided to App.net

~~~ js
{
    "type": "com.example.test",
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
        "file_token_read": "new_file_token",
        "file_id": "1",
        "complete": true,
        "mime_type": "image/png",
        ...other File object values...
        "other_values": "are preserved"
    }
}
~~~


### `oembed` format

This format can only be used with the `net.app.core.oembed` annotation, not with 3rd party annotations.

#### Provided to App.net

~~~ js
{
    "type": "net.app.core.oembed",
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
    "type": "net.app.core.oembed",
    "value": {
        "file_token_read": "new_file_token",
        "file_id": "1",
        "url_immediate": "https://...",
        "url_immediate_expires": "2012-01-01T01:00:00Z",
        "version": "1.0",
        "type": "photo",
        ...other oembed values...
        "other_values": "are preserved"
    }
}
~~~

In addition to the standard oembed fields, App.net will also add fields for `file_token_read` and `file_id` to the OEmbed data. If the OEmbed data is not public, the OEmbed `url` field will expire at the time indicated in `url_expires`.

If the OEmbed data is public, `url` will be a permanent url which always redirects to the image. In this case, an additional field `url_immediate` will provide the current value for the file so you can avoid the redirect. (This expires at `url_immediate_expires`). `thumbnail_url` and `thumbnail_large_url` (described below) also use this same url patterns.

We generate `thumbnail_url` from the [`image_thumb_200s` derived file](http://developers.app.net/docs/resources/file/#derived-files). If the image is smaller than 200x200, then we use the image as its own thumbnail. If we have a larger derived file (`image_thumb_960r`), then we will also include `thumbnail_large_url`, `thumbnail_large_width`, `thumbnail_large_height`, etc that correspond to the larger thumbnail.

If the file has a [`net.app.core.oembed.metadata` annotation](../annotations/net.app.core.oembed.metadata.md), it will be used to generate the OEmbed output. We replace `poster_key`, `thumbnail_key`, and `url_key` fields with `poster_url`, `thumbnail_url`, and `url` fields containing links to the corresponding derived files. If a `_key` field is provided but left empty, we do the replacement with a link to the root file.

#### URL Lifetimes

Note that some extra fields are returned from the API depending on whether the parent object is public or not. For content that is public, like posts, messages in public channels, annotations on user objects, etc., we include a URL in the `url` field which will redirect you to the content in question so long as it is still public; we also include `url_immediate` and `url_immediate_expires` fields if you wish to avoid the extra HTTP request. URLs returned in the `url_immediate` field are good for at least 1 hour after fetching the object from the App.net API.

For private content, we return a short-lived URL in the `url` field and a `url_expires` parameter. URLs returned in this field are good for at least 1 hour after fetching the object from the App.net API.

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `file_token` | Required | string | A valid file token that App.net returned when you uploaded a file.|
| `format` | Required | string | Either `metadata`, `oembed`, or `url` depending on what data you want provided for this file. |
| `file_id` | Required | string | The id of the file. |

<!-- provide a way to contact you -->
## Maintainers
* Mark Thurman ([@mthurman](https://alpha.app.net/mthurman), [mthurman@app.net](mailto:mthurman@app.net))

<!-- provide references to compatible apps / service -->
## Used by
* [Alpha](https://alpha.app.net/)
* [Omega](https://omega.app.net/)

<!-- provide references to related annotations -->
## Related annotations
* [+net.app.core.file_list](+net.app.core.file_list.md)
* [net.app.core.attachments](../annotations/net.app.core.attachments.md)
* [net.app.core.oembed](../annotations/net.app.core.oembed.md)
* [net.app.core.oembed.metadata](../annotations/net.app.core.oembed.metadata.md)
