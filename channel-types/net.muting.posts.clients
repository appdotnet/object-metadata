<!-- give your channel type a title -->
# Channels for saving muted hashtags, threads and clients

<!-- specify the channel type -->
> ### net.muting.posts.clients
> ### net.muting.posts.threads
> ### net.muting.posts.hashtags

<!-- provide a description for this channel type's behavior -->
Based on discussions with [@matigo](https://app.net/matigo) and [@33mhz](https://app.net/33mhz) I came up with this setup, for each type of mutable object one channel per user. In this case 3 channels: Hashtags, Threads and Clients. Each channel will have an annotation because those are mutable. The annotation holds an array of muted ids (tags, thread ids, client ids) for that particular object. I used id for all 3 objects to make the naming convention a bit more uniform. For the channel name I tried to make it generic and 'ready for future’. For example net.muting.messages.threads would be possible. I don’t want to put a product name in the channel or annotation types but keep things generic. But in the end it doesn’t really matter of course. The values are what matters.

This is how Chimp stores it now, just 3 arrays of ids. At the moment there is no option for a user to see the lists of muted ids in Chimp, but ids can be unmuted by the user by touch&holding a particular muted post. Chimp shows muted posts as such in one line of text which states the type of mute and who created the post. A single tap on it will just show that one post and keep all the rest muted.

##Hashtags

###Channel
“type”: "net.muting.posts.hashtags"

###Annotation
"type": “muted.tags"
"value": {
  "ids": [{’superbowl2016’:1464739200}, {‘crap’:0}, {‘spam’:0}]
}

##Threads

###Channel
“type”: "net.muting.posts.threads"

###Annotation
"type": “muted.threads"
"value": {
  "ids": [{‘12345’:0}, {‘666’:0}, {‘98765’:0}]
}

##Clients

###Channel
“type”: "net.muting.posts.clients"

###Annotation
"type": “muted.clients"
"value": {
  "ids": [{‘decaffe’:0}, {‘1337af’:0}, {‘def789’:0}]
}

##Creating the channels

First find users’ subscribed channels of type X, use first one ever created to make sure no rogue channel is used
If no channel of type X found, create it. public: false

If something goes wrong during development/testing of a channel be sure to deactivate the channel https://developers.app.net/reference/resources/channel/lifecycle/#deactivate-a-channel This way it won't show up in the query for the channels anymore.

<!-- provide a way to contact you -->
## Maintainers
* [Steven van Loef](http://www.yellowdice.com/) ([@ludolphus](https://app.net/ludolphus))

<!-- provide references to compatible apps / service -->
## Used by
* [Chimp](http://chimp.li/chimp)

<!-- provide references to related entries -->
## Related entries
* net.muting.posts.hashtags
* net.muting.posts.threads
