<!-- give your channel type a title -->
### Private Message

<!-- specify the channel type -->
> #### net.app.core.pm

<!-- provide a description for this channel type's behavior -->
This channel type is for private messages between 2 or more people. As a core Channel type, it has some special restrictions designed to simplify adoption for developers. 

Private message channels enforce that there is at least one non-owner user_id in the writers ACL and that both ACLs are immutable. Messages with the machine_only flag set are disallowed (though, of course, annotations are permitted when accompanied with text.)

In addition, this channel type differs from others in that it is designed to provide a simple, combined API for channel creation, reuse and message sending. You can only create net.app.core.pm channels via the special endpoint for doing so.

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to compatible apps / service -->
## Used by 
* [Omega](https://omega.app.net/)

<!-- provide references to related entries -->
## Related entries
