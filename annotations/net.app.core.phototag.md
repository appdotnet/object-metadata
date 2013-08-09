<!-- give your annotation a title -->
# Phototag

<!-- specify the "type" for your annotation -->
> ### net.app.core.phototag

<!-- provide a description of what your annotation represents -->
Tag App.net [Users](http://developers.app.net/docs/resources/file/) in a photo.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

### Provided to App.net
~~~ js
{
    "type": "net.app.core.phototag",
    "value": {
        "+net.app.core.user": {
            "user_id": "1",
            "format": "basic"
        },
        "x": 50,
        "y": 50,
    }
}
~~~

### Returned by API

~~~ js
{
    "type": "net.app.core.phototag",
    "value": {
        "x": 50,
        "y": 50,
        "id": "1",
        "username": "mthurman",
        "name": "Mark Thurman",
        "avatar_image": {
            ...
        }
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `+net.app.core.user` | Required | Object | An object that matches the [+net.app.core.user](../annotation-replacement-values/+net.app.core.user.md) validations. For this annotation, the only `format` allowed is `basic`|
| `x` | Required | integer | The x coordinate where the user appears, as a percentage between 0 and 100 from the left of the photo. |
| `y` | Required | integer | The y coordinate where the user appears, as a percentage between 0 and 100 from the top of the photo. |

<!-- provide a way to contact you -->
## Maintainers
* App.net core team

<!-- provide references to compatible apps / service -->
## Used by

<!-- provide references to related annotations -->
## Related annotations
* [+net.app.core.user](../annotation-replacement-values/+net.app.core.user.md)
