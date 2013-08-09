# User

<!-- specify the "key" for the replacement value -->
> ### +net.app.core.user

<!-- provide a description of the replacement value -->
This dynamically inserts information about an App.net [User](http://developers.app.net/docs/resources/user/) into an annotation. The User information is merged with any other values to form a single object.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

### `basic` format

#### Provided to App.net
~~~ js
{
    "type": "com.example.test",
    "value": {
        "+net.app.core.user": {
            "user_id": "1",
            "format": "basic",
        },
        "other_values": "are preserved"
    }
}
~~~

#### Returned by API
~~~ js
{
    "type": "com.example.test",
    "value": {
        "id": "1",
        "username": "mthurman",
        "name": "Mark Thurman",
        "avatar_image": {
            ...
        },
        "other_values": "are preserved"
    }
}
~~~


### `full` format

#### Provided to App.net

~~~ js
{
    "type": "com.example.test",
    "value": {
        "+net.app.core.user": {
            "user_id": "1",
            "format": "full",
        },
        "other_values": "are preserved"
    }
}
~~~

#### Returned by API

~~~ js
{
    "type": "com.example.test",
    "value": {
        "id": "1",
        "username": "mthurman",
        "name": "Mark Thurman",
        "avatar_image": {
            ...
        },
        "description": {
            ...
        },
        ...other User object values...
        "other_values": "are preserved"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `user_id` | Required | string | The user id. If the user id is `me` the current authenticated user will be used. You can also specify `@username` as a `user_id`. |
| `format` | Required | string | Either `basic` or `full` depending on what data you want provided for this user. |

<!-- provide a way to contact you -->
## Maintainers
* Mark Thurman ([@mthurman](https://alpha.app.net/mthurman), [mthurman@app.net](mailto:mthurman@app.net))

<!-- provide references to compatible apps / service -->
## Used by
* None yet; be the first!

<!-- provide references to related annotations -->
## Related annotations
* [+net.app.core.file](+net.app.core.file.md)
* [+net.app.core.place](+net.app.core.place.md)
