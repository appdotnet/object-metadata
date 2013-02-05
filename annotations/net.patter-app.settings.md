<!-- give your annotation a title -->
# Patter Room Settings

<!-- specify the "type" for your annotation -->
> ### net.patter-app.settings

<!-- provide a description of what your annotation represents -->
Patter rooms are of type net.patter-app.room and should always include
this settings annotation to provide additional information about the
room and how it should be displayed.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Examples

~~~ js
{
    "type":"net.patter-app.room",
    "annotations":[
      {
        "type":"net.patter-app.settings",
        "value":{
          "categories":[
            "tech"
          ],
          "name":"Welcome to Patter",
          "blurb":"A room for new users. Feel free to ask questions and try things out.",
          "blurb_id":"30951"
        }
      },
      {
        "type":"net.app.core.fallback_url",
        "value":{
          "url":"http:\/\/patter-app.net\/room.html?channel=964"
        }
      }
    ]
  }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields 

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `name` | Required  | string | User-facing name for the room. Need not be unique. |
| `blurb` | Optional | string | User description of the room. |
| `categories` | Optional | list of strings | Zero or more identifiers categorizing the room (see below). |
| `blurb_id` | Optional | string | Message id of channel invite to the room. |

## Notes

The blurb, categories, and blurb_id fields are mostly used when a user wishes to invite others to the room. A publicly-promoted room should have both a blurb and a blurb_id.

The blurb_id indicates a net.app.core.channel.invite message posted to channel 1614. When a user wishes to remove their channel from promotion, that message should be removed and the blurb, categories, and blurb_id fields should be removed from the channel annotation.

categories is a list of identifiers. The following identifiers are recognized by patter-app.net: 'fun', 'lifestyle', 'profession', 'language', 'community', 'tech', 'event'. If a channel does not have a recognized category, it should be listed as a 'general' room.

<!-- provide a way to contact you -->
## Maintainers
* [Jonathon Duerig](http://jonathonduerig.com) ([@duerig](https://alpha.app.net/duerig))

<!-- provide references to compatible apps / service -->
## Used by
* [Patter](http://patter-app.net)
* [Felix](http://share-app.net)

<!-- provide references to related annotations -->
## Related annotations

net.patter-app.room
net.app.core.channel.invite
net.app.core.fallback_url
