<!-- give your annotation a title -->
# Blog

<!-- specify the "type" for your annotation -->
> ### net.app.core.directory.blog

<!-- provide a description of what your annotation represents -->
A pointer to the user's blog.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "net.app.core.directory.blog",
    "value": {
        "url": "http://myawesomeblog.com",
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields 

| Field | Required? | Type   | Description                              |
| ----- | --------- | ----   | -----------                              |
| `url` | Required  | string | A valid URL pointing to the User's blog. |

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to compatible apps / service -->
## Used by 
* [App.net account settings](https://account.app.net/settings/)

<!-- provide references to related annotations -->
## Related annotations