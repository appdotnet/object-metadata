<!-- give your annotation a title -->
### Language

<!-- specify the "type" for your annotation -->
> ### net.app.core.language

<!-- provide a description of what your annotation represents -->
The language annotation allows a User to indicate what language this post or message was written in. We suggest you add this annotation to a post or message if you have an explicit indication from the user of which language it was written in, or a reasonable estimate, e.g., the locale of the keyboard used to compose the post, metadata from an external feed, etc.

If your application is **consuming** this annotation, we recommend that you fall back to the `locale` field on the User object which created the object in order to determine the effective language of a post.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "net.app.core.language",
    "value": {
        "language": "en",
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `language` | Required | string | A valid ISO 639-1 language code. Note that we only accept a subset of language codes right now. Please see [our current list](https://github.com/appdotnet/api-spec/wiki/Language-codes) of accepted language codes. If we're missing your language, please [open an issue](https://github.com/appdotnet/api-spec/issues). |

<!-- provide a way to contact you -->
## Maintainers
* App.net core team

<!-- provide references to compatible apps / service -->
## Used by

* Riposte
* hAppy

<!-- provide references to related annotations -->
## Related annotations
