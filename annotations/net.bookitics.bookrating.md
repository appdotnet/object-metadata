<!-- give your annotation a title -->
# Book rating

<!-- specify the "type" for your annotation -->
> ### net.bookitics.bookrating

<!-- provide a description of what your annotation represents -->
Identifies a post as a book rating and contains additional book rating data.

In addition to the annotation described here, book rating posts may contain an attached book cover image which is provided via the standard App.net mechanism using a net.app.core.oembed.

Also the standard hashtag mechanism is used to tag book ratings in order to define to which genres the rated books belongs.

The post text contains:
  * As much of the author and title of the book as fits into the post text
  * As much of the first paragraph of the review as fits into the post text
  * Five stars that reflect the rating of the app by being filled or empty (e.g. ★★★☆☆) which is also a link to bookitics.net showing the full text of the review
  * The tags given by the user

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type\": "net.bookitics.bookrating",
    "value": {"
        "author": "James Blish",
        "title": "Cities in Flight"
        "rating": 5,
        "short_review": "This is probably the only book I reread twice. Captivating stories and amazing ideas at a great scale with cities and even planets flying through the universe and having great adventures."
        "full_review_url": "http://beeger.net/2014/03/cities-in-flight/"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `author` | Optional | string | The names of the authors of the book |
| `title` | Required | string | The title of the book. |
| `rating` | Required | integer | A rating of the book between 1 (lowest) and 5 (highest). |
| `short_review` | Optional | string | A short review of the book.|
| `full_review_url` | Optional | string | The URL of a longer review of the book |


<!-- provide a way to contact you -->
## Maintainers
* Robert Beeger [@robertbeeger](https://alpha.app.net/robertbeeger), [robert@beeger.net](mailto:robert@beeger.net)

<!-- provide references to compatible apps / service -->
## Used by
* [Bookitics](http://bookitics.net)

<!-- provide references to related annotations -->
## Related annotations
* [net.app.core.oembed.md](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.oembed.md)
