# App.net Object Metadata

Many of the objects used by the App.net API can be enhanced by third party developers through the use of special metadata. Users, Posts, Channels and Messages can be augmented using [annotations](http://developers.app.net/docs/meta/annotations/), and Channels can be additionally augmented using [channel types](http://developers.app.net/docs/resources/channel/#channel-types). Annotations can be dynamically altered using [annotation replacement values](http://developers.app.net/docs/meta/annotations/#annotation-replacement-values)

This repository serves to document metadata formats in the ecosystem and to encourage collaboration between third party developers in defining new and refining existing metadata formats.

### What's here

The annotations, annotation-replacement-values, and channel-types folders contains a single documentation file in Markdown format for each metadata standard that has been submitted to the repository. These files are arranged alphabetically but otherwise are unordered / uncategorized. We'll be examining options for further organizing these as the pool of entries expands.

### Adding new entries

To submit a new entry, take the following steps:

* [Fork this repository](https://help.github.com/articles/fork-a-repo)
* In your fork, create a new Markdown file in the appropriate directory with a name matching the "type" for your metadata. For annotations, you can view the raw text for the [crosspost annotation](https://raw.github.com/appdotnet/object-metadata/master/annotations/net.app.core.crosspost.md) as a formatting guide. For channel types you can view the raw text for the [pm channel](https://raw.github.com/appdotnet/object-metadata/master/channel-types/net.app.core.pm.md).  _Note: while the App.net API does not prevent multiple annotations / channels types from declaring the same "type", any **new** entry you submit here should not conflict with an existing entry._
* Commit your changes and [submit a pull request](https://help.github.com/articles/using-pull-requests) for the new file. All structurally valid entries will be accepted, but we ask that you focus on submitting annotations that are useful candidates for other developers to utilize.

### Modifying existing entries

To modify an existing entry, you should perform the same steps as above as necessary, committing your updates and submitting a pull request. 

Anyone can issue a pull request for changes to any entry. However, all requests will be approved (merged) by App.net staff in consultation with the existing maintainers specified in the current entry.

### Collaborating

One of our goals for creating this repository is to foster more developer collaboration. We hope developers make extensive use of the [object metadata issue tracker](https://github.com/appdotnet/object-metadata/issues) for this purpose. The issue tracker is also a good place to discuss how we can make this documentation process better!

### Your host

This repository is maintained by [@orian](https://alpha.app.net/orian), App.net's Developer Advocate.
