<!-- give your channel type a title -->
# Journal

<!-- specify the channel type -->
> ### net.app.ohai.journal

<!-- provide a description for this channel type's behavior -->
This channel type represents a user's personal journal containing messages referred to as "entries". Entries may 

### Finding the Journal

A user may only have one journal channel. However, it is possible for them to be subscribed to more than one. A user's journal may be found by getting the user's subscribed channels of type `net.app.ohai.journal`. If they have more than one, filter to channels owned by the authenticated user that have an immutable writer ACL containing only the authenticated user and a mutable reader ACL. If there is still more than one, find the channel with the oldest channel ID.

### Creating Journal Entries

Any application can post entries into a user's journal. If you find a journal using the above algorithm, developers should show UI to allow the user to post entries into a journal. For example, a photo-sharing app that allows posting photos to App.net and Twitter could also add a button to share that photo to a journal. If you do not detect a journal, do not create a new journal channel, and do not show the user this option, as it may be confusing.

It should be noted that any application supporting any kind of data can be published into a journal. For example, an application which allows users to "check in" to a movie can publish a custom annotation into the journal, even if it is not supported by current applications. The important thing to consider is that a user must intend to publish into their journal; manual user action must be taken to publish, or the user must have manually enabled an automatic publish process if your app chooses to support it. Users should not have their journals cluttered by apps without intent. **Apps may be filtered out by journal client apps if they publish without user intent.** This is a very important rule, so please respect it.

### Showing Journal Entries

When the user logs in, look to see if they already have a journal using the above algorithm. If they do have one, download the entire set of all messages within the channel and store them locally. If they do not have a journal channel, create one. A new journal must have the following properties:

- the type `net.app.ohai.journal`
- an immutable writer ACL that only contains the current user
- a mutable reader ACL that contains nobody

Any kind of set of annotations can be contained in posts, so very strict validation of all messages must be used. Clients should not crash or otherwise fail if a malformed annotation is included. Clients should only show entries that conform to certain requirements (for example, Ohai 1.0 only shows entries with locations attached, optionally with photos). Entries may optionally contain text, so API requests for entries should include machine-only messages. Entries are almost always annotated, so annotations should be requested as well.

<!-- provide a way to contact you -->
## Maintainers
* [Steve Streza](http://stevestreza.com) ([@SteveStreza](https://alpha.app.net/SteveStreza))

<!-- provide references to compatible apps / service -->
## Used by 
* [Ohai](http://ohaiapp.net)

<!-- provide references to related entries -->
## Related entries
