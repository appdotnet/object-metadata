<!-- give your channel type a title -->
# Broadcast

<!-- specify the channel type -->
> ### net.app.core.broadcast

<!-- provide a description for this channel type's behavior -->
Broadcast channels are meant for low-volume, high-value updates that users explicitly opt-in to.

- Broadcast channels must not have multiple writers. If you'd like multiple people to be able to publish to a Broadcast channel, you must make them all editors.
- Broadcast channels must have a mutable ACL for both editors and writers.
- Broadcast channels can have an unlimited number of readers explicitly specified.
- You *cannot* auto-subscribe anyone to Broadcast channels. They are opt-in.

### Reserved annotations for Broadcasts

* [net.app.core.fallback_url](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.fallback_url.md): All Broadcast channels (and the messages they contain) have a fallback url annotation that is automatically filled in by the App.net API. Thus, this annotation type is read only for Broadcast channels.
* [net.app.core.broadcast.metadata](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.broadcast.metadata.md): This annotation can only be used with Broadcast channels. It provides extra information about the content of the Broadcast channel.
* [net.app.core.broadcast.message.metadata](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.broadcast.message.metadata.md): This annotation can only be used with Messages in Broadcast channels. It provides extra information about a Broadcast message.


<!-- provide a way to contact you -->
## Maintainers
* App.net core team

<!-- provide references to compatible apps / service -->
## Used by 
* [App.net Broadcast](https://broadcast.app.net/)
* [App.net Mobile](https://app.net/mobile)

<!-- provide references to related entries -->
## Related entries
