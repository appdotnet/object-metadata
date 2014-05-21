<!-- give your annotation a title -->
# App

<!-- specify the "type" for your annotation -->
> ### net.appiast.app.XXXXXX

<!-- provide a description of what your annotation represents -->
Identifies the app a post is rating. The Xs are replaced by the id of the app the post is rating.

To ensure uniqueness of app ids, they have prefixes that identify them as belonging to a specific app store or other source of apps. Ids from the Apple Mac, iPhone and iPad app stores are prefixed with an "a". So a post rating the app "Appiast" which has the id 868774614 will have an annotation with the name "net.appiast.app.a868774614"

This annotation is used to find all app ratings for a specific app.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type\": "net.appiast.app.a868774614",
    "value": {"
        "answer": "42",
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

There are no used fields in this annotation. Appiast generates the field "answer" with the value "42", because an annotation must have a value.

<!-- provide a way to contact you -->
## Maintainers
* Robert Beeger [@robertbeeger](https://alpha.app.net/robertbeeger), [robert@beeger.net](mailto:robert@beeger.net)

<!-- provide references to compatible apps / service -->
## Used by
* [Appiast](http://appiast.net)

<!-- provide references to related annotations -->
## Related annotations
* [net.appiast.apprating](net.appiast.apprating.md)
