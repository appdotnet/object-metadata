<!-- give your annotation a title -->
# Display Date

<!-- specify the "type" for your annotation -->
> ### net.app.ohai.displaydate

<!-- provide a description of what your annotation represents -->
The display date annotation is meant to specify a custom date to associate with a message. It should only be used when a person intended to create the post with a different date. For example, if your app supports posting offline, an offline post could contain this annotation for when the post was created locally. When it gets posted to the network, it will have a different creation date, but the annotation can accurately represent when the user created the post or message.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "net.app.ohai.displaydate",
    "value": {
        "date": "2013-06-02T18:51:34Z",
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field         | Required? | Type   | Description                                                     |
| -----         | --------- | ----   | -----------                                                     |
| date          | Required  | string | The time at which the message was created in ISO 8601 format.   |

<!-- provide a way to contact you -->
## Maintainers
* [Steve Streza](http://stevestreza.com) ([@SteveStreza](https://alpha.app.net/SteveStreza))

<!-- provide references to compatible apps / service -->
## Used by 
* [Ohai](http://ohaiapp.net)

<!-- provide references to related annotations -->
## Related annotations