<!-- give your channel type a title -->
# Channels for saving muted hashtags, threads and clients

<!-- specify the channel type -->
> ### net.muting.posts.clients
> ### net.muting.posts.threads
> ### net.muting.posts.hashtags

<!-- provide a description for this channel type's behavior -->
The app.net API provides muting options for users and channels but not for any other object types. We thought it would be useful to have more muting options available to the user to prevent spam in post timelines and other unwanted content. We decided to add muting options for hashtags, threads and clients.

Based on discussions with [@matigo](https://app.net/matigo) and [@33mhz](https://app.net/33mhz) I ([@ludolphus](https://app.net/ludolphus)) came up with this setup, for each type of mutable object one channel per user. In this case 3 channels: Hashtags, Threads and Clients. Each channel will have an annotation because those are mutable. The annotation holds an array of muted ids (tags, thread ids, client ids) for that particular object.  For the channel name I tried to make it generic and 'ready for future’. For example net.muting.messages.threads would be possible. I don’t want to put a product name in the channel or annotation types but keep things generic. But in the end it doesn’t really matter of course. The keys and values are what matters.

This is how Chimp stores it now, just 3 arrays of ids. At the moment there is no option for a user to see the lists of muted ids in Chimp, but ids can be unmuted by the user by touch&holding a particular muted post. Chimp shows muted posts as such in one line of text which states the type of mute and who created the post. A single tap on it will just show that one post and keep all the rest muted.

Broadsword has support for hashtag muting based on this specification.

##Hashtags

###Channel
“type”: "net.muting.posts.hashtags"

###Annotation
```
"type": “muted.tags"
"value": {
  "ids": [
    {
      'name':'superbowl2016',
      'expire_at':1464739200
    },
    {
      'name':'crap',
      'expire_at':0
    },
    {
      'name':'spam',
      'expire_at':0
    }
  ]
}
```
The key 'expire_at' is optional (or set to 0), it doesn't have to be written or used by a client. If used it specifies a timestamp in UNIX epoch when the muting for the object should expire. In this case a client may decide to remove to muted object from the annotation.
##Threads

###Channel
“type”: "net.muting.posts.threads"

###Annotation
```
"type": “muted.threads"
"value": {
  "ids": [
    {
      'id':'12345',
      'expire_at': 0
    },
    {
      'id':'666',
      'expire_at':0
      },
    {
      'id':'98765',
      'expire_at':0
    }
  ]
}
```
The key 'expire_at' is optional (or set to 0), it doesn't have to be written or used by a client. If used it specifies a timestamp in UNIX epoch when the muting for the object should expire. In this case a client may decide to remove to muted object from the annotation.

Suggestion for a UI to manage muted threads: use the [Retrieve multiple posts endpoint](https://developers.app.net/reference/resources/post/lookup/#retrieve-multiple-posts) to retrieve the first post of all muted threads. Show these to the user and let them unmute the thread(s).
##Clients
###Channel
“type”: "net.muting.posts.clients"

###Annotation
```
"type": “muted.clients"
"value": {
  "ids": [
    {
      'name': 'Alpha',
      'id': 'caYWDBvjwt2e9HWMm6qyKS6KcATHUkzQ',
      'expire_at':0
    },
    {
      'name': 'dlvrit',
      'id': 'AnL26PHsjb4MbzDkwJcJD9qUMsem56dP',
      'expire_at':0
    },
    {
      'name': 'IFTTT',
      'id': 'GzJVygE6vpLbabgBtEKzEKH8ASzS6mF3',
      'expire_at':0
    }
  ]
}
```
For clients the 'name' key is added to make it easier for a UI that manages muted objects to show the user which clients are muted. The 'id' key should be used when filtering posts.

The key 'expire_at' is optional (or set to 0), it doesn't have to be written or used by a client. If used it specifies a timestamp in UNIX epoch when the muting for the object should expire. In this case a client may decide to remove to muted object from the annotation.
##Creating the channels

First find users’ subscribed channels of type X, use first one ever created to make sure no rogue channel is used
If no channel of type X found, create it. Make sure to set the public key to false (this makes the channel private to the user).

If something goes wrong during development/testing of a channel be sure to deactivate the channel https://developers.app.net/reference/resources/channel/lifecycle/#deactivate-a-channel This way it won't show up in the query for the channels anymore.

<!-- provide a way to contact you -->
## Maintainers
* [Steven van Loef](http://www.yellowdice.com/) ([@ludolphus](https://app.net/ludolphus))

## Contributors
* [@33mhz](https://app.net/33mhz)
* [@matigo](https://app.net/matigo)

<!-- provide references to compatible apps / service -->
## Used by
* [Chimp](http://chimp.li/chimp)
* [Broadsword](http://broadsword.io/)

<!-- provide references to related entries -->
## Related entries
* net.muting.posts.hashtags
* net.muting.posts.threads
