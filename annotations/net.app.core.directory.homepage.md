<!-- give your annotation a title -->
# Homepage

<!-- specify the "type" for your annotation -->
> ### net.app.core.directory.homepage

<!-- provide a description of what your annotation represents -->
A pointer to the user's homepage.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "net.app.core.directory.homepage",
    "value": {
        "url": "http://thisisme.com",
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type   | Description                                  |
| ----- | --------- | ----   | -----------                                  |
| `url` | Required  | string | A valid URL pointing to the User's homepage. |

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to compatible apps / service -->
## Used by
* [App.net account settings](https://account.app.net/settings/)

<!-- provide references to related annotations -->
## Related annotations