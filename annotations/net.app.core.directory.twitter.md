<!-- give your annotation a title -->
### Twitter

<!-- specify the "type" for your annotation -->
> ### net.app.core.directory.twitter

<!-- provide a description of what your annotation represents -->
A pointer to the user's Twitter account. 

You can use either the username (which can be changed and so might become inaccurate over time) or the user id (which can't), or both. 

If using both, then they ought to match (at least at the time of posting). However clients may not wish to rely upon this, and opt to look up the Twitter username from the id themselves.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Examples

~~~ js
{
    "type": "net.app.core.directory.twitter",
    "value": {
        "username": "appdotnet",
    }
}
~~~

~~~ js
{
    "type": "net.app.core.directory.twitter",
    "value": {
        "user_id": "123456789",
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field    | Required? | Type   | Description                                       |
| -----    | --------- | ----   | -----------                                       |
| username | Optional  | string | A Twitter username representing the App.net User. |
| user_id  | Optional  | string | A Twitter user id representing the App.net User.  |

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to compatible apps / service -->
## Used by
* [App.net account settings](https://account.app.net/settings/)

<!-- provide references to related annotations -->
## Related annotations
