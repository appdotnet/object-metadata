<!-- give your annotation a title -->
# Channel Avatar

<!-- specify the "type" for your annotation -->
> ### net.app.channel.avatar_image

<!-- provide a description of what your annotation represents -->
Add an avatar to channels of type patter and broadcast (potentially other channels as well)

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

### Provided to App.net
~~~ js
{
    "type": "net.app.channel.avatar_image",
    "value": {
          {
            "url": 'URL_TO_AVATAR',
            "width": '200',
            "height": '200',
          }
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| url | Required | string | url pointing to the avatar image |
| width | Required | string | width of the avatar, clients can scale as needed |
| height | Required | string | height of the avatar |

<!-- provide a way to contact you -->
## Maintainers
* [@ludolphus](https://alpha.app.net/ludolphus)

<!-- provide references to compatible apps / service -->
## Used by

* [Chimp](http://chimp.li) for Patter and Broadcast channels Chimp provides a UI to set the avatar
