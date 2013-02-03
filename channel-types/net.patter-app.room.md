<!-- give your channel type a title -->
# Patter Room

<!-- specify the channel type -->
> ### net.patter-app.room

<!-- provide a description for this channel type's behavior -->
This channel type provides public or private chatrooms with modifiable permissions. As a chat room, there will likely be more and shorter messages than a typical channel or post stream. 

Every compliant Patter room has a [net.patter-app.settings](/object-metadata/master/annotations/net.patter-app.settings.md) channel annotation which contains a name for display to a user.

Patter rooms should also have a net.app.core.fallback_url annotation although some legacy channels may not have it.

Patter rooms may be one of three kinds and these are implicitly encoded in the permissions:
* Private Rooms may only be written to or read by users. Both readers and writers should have any_user and public set to false. The members are the user_ids listed in writers and the owner. The user_ids list in readers should be empty.
* Public Rooms may be written to or read by anyone. Both readers and writers should have any_user and public set to true.
* Public Read Rooms can be read by anyone but only written to by members. Readers should have any_user and public set to true. Writers should have any_user and public set to false and user_ids which make up the membership (along with the owner).

Patter rooms usually have editable permissions. But some may have immutable readers, immutable writers, or both. While threading is allowed, many clients will not display threading and instead show all messages as a single flat list of messages.

Most messages have text with optional annotations. Clients should render the text of such messages and ignore any unknown annotations. If a post has no text (machine_only) and has no known annotations, it should be ignored.

The following annotations are common in messages in Patter Rooms:
* [net.patter-app.broadcast](/object-metadata/master/annotations/net.patter-app.broadcast) is used by some clients to indicate messages which have been copied into a post. Clients may indicate these messages visually and provide a way to open the post. The post itself should contain a [net.app.core.cross-post](/object-metadata/master/annotations/net.app.core.cross-post) annotation indicating the Patter Room URL (see below) which the broadcast post came from.
* [net.app.core.oembed](/object-metadata/master/annotations/net.app.core.oembed) can be used to embed images into the chat room. How these are displayed is up to the client.

Patter rooms have a unique canonical URL:

http://patter-app.net/room.html?channel=CHANNELID

This URL should be used when creating a broadcast post with the net.app.core.cross-post annotation (above). Users may also use the URL by hand to invite others to a public room. When encountering such a URL, clients may wish to parse the URL and use a native implementation of Patter rather than treating it as a normal link.

<!-- provide a way to contact you -->
## Maintainers
* [Jonathon Duerig](http://jonathonduerig.com) ([@duerig](https://alpha.app.net/duerig))

<!-- provide references to compatible apps / service -->
## Used by 
* [Patter](http://patter-app.net)

<!-- provide references to related entries -->
## Related entries
