<!-- give your annotation a title -->
# Crosspost

<!-- specify the "type" for your annotation -->
> ### net.app.core.crosspost

<!-- provide a description of what your annotation represents -->
The crosspost annotation is meant to specify the original or canonical source of a Post on App.net from somewhere else on the web.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "net.app.core.crosspost",
    "value": {
        "canonical_url": "https://twitter.com/AppDotNet/status/234705338849443840",
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field         | Required? | Type   | Description                                                 |
| -----         | --------- | ----   | -----------                                                 |
| canonical_url | Required  | string | A valid URL pointing to the source of the original content. |

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to compatible apps / service -->
## Used by
* [Alpha](https://alpha.app.net)
* [Patter](http://patter-app.net)

<!-- provide references to related annotations -->
## Related annotations