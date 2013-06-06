<!-- give your annotation a title -->
# Embedded Media

<!-- specify the "type" for your annotation -->
> ### net.app.core.oembed

<!-- provide a description of what your annotation represents -->
The embedded media annotation specifies an image, video, or other rich content that should be displayed with this post. It uses the [JSON oEmbed specification](http://oembed.com). We only support the `photo`, `video`, and `rich` oEmbed types.

We highly recommend providing the ```embeddable_url``` attribute so other clients can request different oEmbed details for this object from the original oEmbed provider (if there is one).

<!-- provide at least one example of what your annotation might look like in the wild -->
## Examples

### Photo

~~~ js
{
    "type": "net.app.core.oembed",
    "value": {
        "version": "1.0",
        "type": "photo",
        "width": 240,
        "height": 160,
        "title": "ZB8T0193",
        "url": "http://farm4.static.flickr.com/3123/2341623661_7c99f48bbf_m.jpg",
        "author_name": "Bees",
        "author_url": "http://www.flickr.com/photos/bees/",
        "provider_name": "Flickr",
        "provider_url": "http://www.flickr.com/",
        "embeddable_url": "http://www.flickr.com/photos/bees/2341623661/"
    }
}
~~~

### Video

~~~ js
{
    "type": "net.app.core.oembed",
    "value": {
        "version": "1.0",
        "type": "video",
        "provider_name": "YouTube",
        "provider_url": "http://youtube.com/",
        "width": 425,
        "height": 344,
        "title": "Amazing Nintendo Facts",
        "author_name": "ZackScott",
        "author_url": "http://www.youtube.com/user/ZackScott",
        "html":
            "<object width=\"425\" height=\"344\">
                <param name=\"movie\" value=\"http://www.youtube.com/v/M3r2XDceM6A&fs=1\"></param>
                <param name=\"allowFullScreen\" value=\"true\"></param>
                <param name=\"allowscriptaccess\" value=\"always\"></param>
                <embed src=\"http://www.youtube.com/v/M3r2XDceM6A&fs=1\"
                    type=\"application/x-shockwave-flash\" width=\"425\" height=\"344\"
                    allowscriptaccess=\"always\" allowfullscreen=\"true\"></embed>
            </object>",
        "embeddable_url": "http://youtube.com/watch?v=M3r2XDceM6A"
    }

}
~~~

### HTML5 Video

~~~ js
{
    "type": "net.app.core.oembed",
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
        "url": "http://vjs.zencdn.net/v/oceans.mp4",
        "url_alternate": "http://vjs.zencdn.net/v/oceans.webm",
        "poster_url": "http://www.videojs.com/img/poster.jpg",
    }

}
~~~

### Rich

~~~ js
{
    "type": "net.app.core.oembed",
    "value": {
        "provider_url": "http://soundcloud.com",
        "description": "Listen to Merenti - La Karambaa by M\u00e9renti | Create, record and share the sounds you create anywhere to friends, family and the world with SoundCloud, the world's largest community of sound creators.",
        "title": "Merenti - La Karambaa by M\u00e9renti",
        "html": "<iframe width=\"500\" height=\"166\" scrolling=\"no\" frameborder=\"no\" src=\"http://w.soundcloud.com/player/?url=http%3A%2F%2Fapi.soundcloud.com%2Ftracks%2F6733249&show_artwork=true&maxwidth=900\"></iframe>",
        "author_name": "M\u00e9renti",
        "height": 166,
        "width": 500,
        "thumbnail_url": "http://i1.sndcdn.com/artworks-000003051440-mm2z46-t500x500.jpg?d95e793",
        "thumbnail_width": 500,
        "version": "1.0",
        "provider_name": "SoundCloud",
        "type": "rich",
        "thumbnail_height": 500,
        "author_url": "http://soundcloud.com/mrenti"
        "embeddable_url": "http://soundcloud.com/mrenti/merenti-la-karambaa"
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
| `url` | Required if `type="photo"` or `type="html5video"` | string | The source URL for the image or video. |
| `html` | Required if `type="video"` or `type="rich"` | string | The HTML to display the rich or video content. It should have no margins or padding. App.net does <strong>no validation</strong> of this field. Please program defensively. You may wish to load this in an off-domain iframe to avoid XSS vulnerabilities. |
| `embeddable_url` | Optional (but recommended) | string | A URL that can be given to an oEmbed provider to recreate the oEmbed data contained in this annotation. This is useful so other clients can get updated information or retrieve a different sized embedding through an oEmbed endpoint. |
| `title` | Optional | string | A title for this embedded content. |
| `author_name` | Optional | string | The author of this embedded content. |
| `author_url` | Optional | string | The URL for the author of this embedded content. |
| `provider_name` | Optional | string | The service that provides this embedded content. |
| `provider_url` | Optional | string | The URL for the service that provides this embedded content. |
| `cache_age` | Optional | integer | How long (in seconds) should clients cache the embedded content. |
| `url_alternate` | Optional | string | An alternate video source URL for an `html5video` (for providing multiple video formats). |
| `poster_url` | Optional | string | A URL to a poster image for an `html5video`. |
| `thumbnail_url` | Optional | string | A URL to an image that represents this resource. If this parameter is specified, `thumbnail_height` and `thumbnail_width` must also be present. |
| `thumbnail_height` | Optional | string | The height of the thumbnail image. If this parameter is specified, `thumbnail_url` and `thumbnail_width` must also be present. |
| `thumbnail_width` | Optional | string | The height of the thumbnail image. If this parameter is specified, `thumbnail_height` and `thumbnail_url` must also be present. |

**`url`, `url_alternate`, `poster_url`, `thumbnail_url`, and `embeddable_url` are processed for [App.net URI templates](http://developers.app.net/docs/meta/entities/#uri-templates) by default. You can turn this behavior off by passing `"process_template": false` as an extra attribute.**

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to compatible apps / service -->
## Used by
* [Alpha](https://alpha.app.net/)
* [Patter](http://patter-app.net)
* [Vidcast](http://vidcast-app.net)

<!-- provide references to related annotations -->
## Related annotations
* [+net.app.core.file](../annotation-replacement-values/+net.app.core.file.md)
* [+net.app.core.file_list](../annotation-replacement-values/+net.app.core.file_list.md)
* [net.app.core.attachments](net.app.core.attachments.md)
