<!-- give your annotation a title -->
# Book

<!-- specify the "type" for your annotation -->
> ### net.bookitics.book.XXXXXX

<!-- provide a description of what your annotation represents -->
Identifies the book a post is rating. The Xs are replaced by the id of the first post to rate a book.

So if the post rates a book that was already rated in the post with the id 4711, the post will have an annotation with the name "net.bookitics.book.4711". The value of the annotation is not relevant. The important thing is that the annotation is present and the post can be found by searching for the annotation.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type\": "net.bookitics.book.4711",
    "value": {"
        "answer": "42",
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

There are no used fields in this annotation. Bookitics generates the field "answer" with the value "42", because an annotation must have a value.

<!-- provide a way to contact you -->
## Maintainers
* Robert Beeger [@robertbeeger](https://alpha.app.net/robertbeeger), [robert@beeger.net](mailto:robert@beeger.net)

<!-- provide references to compatible apps / service -->
## Used by
* [Bookitics](http://bookitics.net)

<!-- provide references to related annotations -->
## Related annotations
* [net.bookitics.bookrating](net.bookitics.bookrating.md)
