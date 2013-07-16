<!-- give your annotation a title -->
# oEmbed Metadata Annotation

<!-- specify the "type" for your annotation -->
> ### net.app.core.oembed.metadata

<!-- provide a description of what your annotation represents -->
An oEmbed Metadata Annotation should only be attached to a File object. It represents additional information used to construct a more complete oEmbed representation of its host file when using the +net.app.core.file replacement annotation with the 'oembed' type.

Using an oEmbed Metadata Annotation can allow for oEmbed representations of photos when App.net can't automatically generate one (i.e. if format isn't `jpg`, `png`, or `gif`).

The `html5video` type is the main use case for this annotation. A video and any necessary extras (multiple formats, thumbnails, etc) can now be represented by a single [File](http://developers.app.net/docs/resources/file/) object and its [derived files](http://developers.app.net/docs/resources/file/#derived-files). This annotation then maps out the pieces. A [+net.app.core.file](../annotation-replacement-values/+net.app.core.file.md) annotation can then generate an oEmbed representation with all the necessary parts to construct an HTML5 Video tag.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Examples

### Photo

~~~ js
{
    "type": "net.app.core.oembed.metadata",
    "value": {
        "version": "1.0",
        "type": "photo",
        "width": 240,
        "height": 160,
    }
}
~~~

### HTML5 Video

~~~ js
{
    "type": "net.app.core.oembed.metadata",
    "value": {
        "version": "1.0",
        "type": "html5video",
        "provider_name": "Video.js",
        "provider_url": "http://www.videojs.com",
        "width": 970,
        "height": 404,
        "title": "Disney Nature's Oceans",
        "author_name": "Disney",
        "author_url": "http://nature.disney.com/oceans",
        "sources": [
            {"type": "video/mp4", "url_key": "mp4"},
            {"type": "video/webm", "url_key": "webm"}
        ]
        "poster_key": "poster",
        "thumbnail_key": "thumb",
        "thumbnail_width": 100,
        "thumbnail_height": 100,
    }
}
~~~



<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

**To correspond with the oEmbed spec, this annotation accepts keys that are not specified below.**

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `type` | Required  | string | `photo`, `video`, `html5video`, or `rich` corresponding to the oEmbed type. |
| `version` | Required | string | Must be `1.0`. |
| `width` | Required | integer | The width in pixels needed to display the embeddable content. |
| `height` | Required | integer | The height in pixels needed to display the embeddable content. |
| `url` | Required if `type="photo"` | string | The source URL for the image or video. |
| `html` | Required if `type="video"` or `type="rich"` | string | The HTML to display the rich or video content. It should have no margins or padding. App.net does <strong>no validation</strong> of this field. Please program defensively. You may wish to load this in an off-domain iframe to avoid XSS vulnerabilities. |
| `sources` | Required if `type="html5video"` | list | A list of up to 5 `{type, url_key}` entries to use in constructing the HTML `<source>` tags. `type` should be a string that can be dropped into the `type` attribute (e.g. `video/mp4` or `video/webm; codecs="vp8.0, vorbis"`). `url_key` must be an existing derived file key. |
| `embeddable_url` | Optional (but recommended) | string | A URL that can be given to an oEmbed provider to recreate the oEmbed data contained in this annotation. This is useful so other clients can get updated information or retrieve a different sized embedding through an oEmbed endpoint. |
| `title` | Optional | string | A title for this embedded content. |
| `author_name` | Optional | string | The author of this embedded content. |
| `author_url` | Optional | string | The URL for the author of this embedded content. |
| `provider_name` | Optional | string | The service that provides this embedded content. |
| `provider_url` | Optional | string | The URL for the service that provides this embedded content. |
| `cache_age` | Optional | integer | How long (in seconds) should clients cache the embedded content. |
| `poster_key` | Optional | string | A derived file key used to populate the `poster_url` field. This field must be an existing derived file key. |
| `thumbnail_key` | Optional | string | A derived file key used to populate the `thumbnail_url` field. If this parameter is specified, `thumbnail_height` and `thumbnail_width` must also be present and `thumbnail_url` must not be. This field must be an existing derived file key. |
| `thumbnail_url` | Optional | string | A URL to an image that represents this resource. If this parameter is specified, `thumbnail_height` and `thumbnail_width` must also be present and `thumbnail_key` must not be. |
| `thumbnail_height` | Optional | string | The height of the thumbnail image. If this parameter is specified, `thumbnail_width` and either `thumbnail_key` or `thumbnail_url` must also be present. |
| `thumbnail_width` | Optional | string | The height of the thumbnail image. If this parameter is specified, `thumbnail_height` and either `thumbnail_key` or `thumbnail_url` must also be present. |

`poster_key`, `thumbnail_key`, and `url_key` fields are validated as an existing [derived key](http://developers.app.net/docs/resources/file/#derived-files) on the annotation's host file. When an oEmbed representation of that file is requested by a [+net.app.core.file](../annotation-replacement-values/+net.app.core.file.md) replacement annotation, these fields are replaced by `poster_url`, `thumbnail_url`, and `url` fields respectively, and populated with links to the corresponding derived files. Specifying one of these `_key` fields as an empty string will cause its replacement will be populated with a link to the root file.

**`url`, `poster_url`, `thumbnail_url`, and `embeddable_url` are processed for [App.net URI templates](http://developers.app.net/docs/meta/entities/#uri-templates) by default. You can turn this behavior off by passing `"process_template": false` as an extra attribute.**

<!-- provide a way to contact you -->
## Maintainers
* Mark Thurman ([@mthurman](https://alpha.app.net/mthurman), [mthurman@app.net](mailto:mthurman@app.net))

<!-- provide references to compatible apps / service -->
## Used by
* None yet; be the first!

<!-- provide references to related annotations -->
## Related annotations
* [+net.app.core.file](../annotation-replacement-values/+net.app.core.file.md)
* [+net.app.core.file_list](../annotation-replacement-values/+net.app.core.file_list.md)
* [net.app.core.attachments](net.app.core.attachments.md)
