<!-- give your annotation a title -->
### Language

<!-- specify the "type" for your annotation -->
> ### net.app.core.language

<!-- provide a description of what your annotation represents -->
The language annotation allows a User to indicate what language this post was written in.

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
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to compatible apps / service -->
## Used by

<!-- provide references to related annotations -->
## Related annotations