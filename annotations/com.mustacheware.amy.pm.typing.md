<!-- give your annotation a title -->
# Typing Presence 

<!-- specify the "type" for your annotation -->
> ### com.mustacheware.amy.pm.typing

<!-- provide a description of what your annotation represents -->
The Typing Presence annotation specifies when the posting user has started or stopped typing something in a private messaging session.

Accepting or emitting this annotation is entirely optional.

This annotation must be supplied as a machine-only post.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example - Start Typing

~~~ js
{
    "type": "com.mustacheware.amy.pm.typing",
    "value": {
        "is_typing": true 
    }
}
~~~

## Example - Stop Typing

~~~ js
{
    "type": "com.mustacheware.amy.pm.typing",
    "value": {
        "is_typing": false 
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field     | Required? | Type    | Description                                                                                       |
| -----     | --------- | ----    | -----------                                                                                       |
| is_typing | Required  | boolean | True if the user has started typing, false if the user stops typing (e.g. clears the text field). |

<!-- provide a way to contact you -->
## Maintainers
* [Steve Streza](http://stevestreza.com) ([@SteveStreza](https://alpha.app.net/SteveStreza), [steve@stevestreza.com](mailto:steve@stevestreza.com))

<!-- provide references to compatible apps / service -->
## Used by
* Forthcoming App

<!-- provide references to related annotations -->
## Related annotations
* N/A
