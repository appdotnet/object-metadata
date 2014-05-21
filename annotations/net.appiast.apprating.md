<!-- give your annotation a title -->
# App rating

<!-- specify the "type" for your annotation -->
> ### net.appiast.apprating

<!-- provide a description of what your annotation represents -->
Identifies a post as an app rating and contains additional app rating data.

In addition to the annotation described here, app rating posts contain an attached app icon image which is provided via the standard App.net mechanism using a net.app.core.oembed.

Also the standard hashtag mechanism is used to tag app ratings in order to define what kind of app the rated app is.

The post text contains
  * the name of the app which is also a link to the app in the app store
  * As much of the app review as fits into the post
  * Five stars that reflect the rating of the app by being filled or empty (e.g. ★★★☆☆) which is also a link to appiast.net showing the full text of the review
  * The tags given by the user

Each app rating post also has a [net.appiast.app.XXXXXX](net.appiast.app.XXXXXX.md) annotation.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type":"net.appiast.apprating",
    "value":{
        "app_name":"Appiast",
        "app_type":"iOS",
        "review":"Appiast is an app for writing and finding reviews of other apps. Reviews ...",
        "full_review_url":"",
        "rating":5,
        "app_id":"868774614"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `app_name` | Required | string | The name of the app |
| `app_type` | Required | string | The type of the app. Currently there are "iOS" and "Mac" |
| `rating` | Required | integer | A rating of the app between 1 (lowest) and 5 (highest). |
| `review` | Optional | string | A short review of the app.|
| `full_review_url` | Optional | string | The URL of a longer review of the app |
| `app_id` | Optional | string | The id of the rated app in the specific app store or other source of apps. |


<!-- provide a way to contact you -->
## Maintainers
* Robert Beeger [@robertbeeger](https://alpha.app.net/robertbeeger), [robert@beeger.net](mailto:robert@beeger.net)

<!-- provide references to compatible apps / service -->
## Used by
* [Appiast](http://appiast.net)

<!-- provide references to related annotations -->
## Related annotations
* [net.appiast.app.XXXXXX](net.appiast.app.XXXXXX.md)
* [net.app.core.oembed.md](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.oembed.md)
