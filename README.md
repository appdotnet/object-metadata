# App.net Annotations Repository 

Annotations are metadata that can be attached to various objects in the App.net system. They allow developers to add additional information to App.net objects outside of the fields App.net has already defined. For more information on the definition and usage of annotations, please [browse the annotations documentation](http://developers.app.net/docs/meta/annotations/).

### Purpose

This repository serves to document active annotations in the ecosystem and to encourage collaboration between third party developers in defining new and refining existing annotations.

### What's here

The annotations folder contains a single documentation file in Markdown format for each annotation that has been submitted to the repository. These files are arranged alphabetically but otherwise are unordered / uncategorized. We'll be examining options for further organizing annotations as the pool of entries expands.

### Adding new annotations 

To submit a new annotation, take the following steps:

* [Fork this repository](https://help.github.com/articles/fork-a-repo)
* In your fork, create a new Markdown file in the annotations directory with a name matching the "type" for your annotation. You should base this file off [net.app.sample.annotation.md](annotations/blob/master/net.app.sample.annotation.md). _Note: while the App.net API does not prevent unrelated annotations from declaring the same "type", any **new** annotation you submit here should not match an existing entry._
* Commit your changes and [submit a pull request](https://help.github.com/articles/using-pull-requests) for the new file. All valid annotations will be accepted, but we ask that you focus on submitting annotations that are useful candidates for other developers to utilize.

### Modifying existing annotations

To modify an existing annotation, you should perform the same steps as above as necessary, committing your updates and submitting a pull request. 

Anyone can issue a pull request for changes to any annotation. However, all requests will be approved (merged) by App.net staff in consultation with existing maintainers specified in the relevant annotation.

### Collaborating on annotations

One of our goals for creating this repository is to foster more developer collaboration on annotations. We hope developers make extensive use of the [annotations issue tracker](annotations/issues) for this purpose. The issue tracker is also a good place to discuss how we can make the annotation documenting process better!

### Your host

This repository is maintained by [@orian](https://alpha.app.net/orian), App.net's Developer Advocate. 
