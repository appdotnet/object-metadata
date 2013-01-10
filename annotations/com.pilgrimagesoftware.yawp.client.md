<!-- give your annotation a title -->
# Yawp Client Info

<!-- specify the "type" for your annotation -->
> ### com.pilgrimagesoftware.yawp.client

<!-- provide a description of what your annotation represents -->
The client annotation is meant to provide information about the version of Yawp that is used to post.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "com.pilgrimagesoftware.yawp.client",
    "value": {
    	"build_date": "Mon Jan 7 19:22:28 PST 2013",
    	"build_number": "118",
        "locale": "en_US",
        "name": "com.pilgrimagesoftware.yawp",
        "version": "1.1"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field         | Required? | Type   | Description                                                    |
| -----         | --------- | ----   | -----------                                                    |
| build_date    | Required  | string | A formatted date string. See the example above for the format. |
| build_number  | Required  | string | The application's internal build number.                       |
| name          | Required  | string | The bundle ID of the application.                              |
| locale        | Required  | string | The locale identifier of the user.                             |
| version       | Required  | string | The version of the application in dotted notation.             |

<!-- provide a way to contact you -->
## Maintainers
* [Paul Schifferer](http://pilgrimagesoftware.com) ([@pilgrim](https://alpha.app.net/pilgrim), [pilgrim@pilgrimagesoftware.com](mailto:pilgrim@pilgrimagesoftware.com))

<!-- provide references to compatible apps / service -->
## Used by
* [Yawp](http://pilgrimagesoftware.com/products/yawp)

<!-- provide references to related annotations -->
## Related annotations