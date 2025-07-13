# WebFeed

A dart package for parsing RSS and Atom feeds.

This repository is a fork of https://github.com/witochandra/webfeed. 
While the orginal repo is very nicely written, it hasn't been updated in 2 years and may be abandoned.

This fork aims to:
1. Fix issues related to the parsing of timezones
2. Add proper parsing of the `media:group` section of YouTube atom feeds (ex: thumbnails).

### Features

- [x] RSS (0.9, 1.0, & 2.0)
- [x] Atom
- [x] Namespaces
    - [x] Media RSS
    - [x] Dublin Core
    - [x] iTunes
    - [x] Syndication

### Installing

Add these lines into your `pubspec.yaml`
```
  webfeed:
    git:
      url: https://github.com/imprologic/webfeed.git
      ref: v0.9.0 

```

Import the package into your dart code using:
```
import 'package:webfeed/webfeed.dart';
```

### Example

To parse string into `RssFeed` object use:
```
var rssFeed = RssFeed.parse(xmlString); // for parsing RSS feed
var atomFeed = AtomFeed.parse(xmlString); // for parsing Atom feed
```

### Preview

**RSS**
```
feed.title
feed.description
feed.link
feed.author
feed.items
feed.image
feed.cloud
feed.categories
feed.skipDays
feed.skipHours
feed.lastBuildDate
feed.language
feed.generator
feed.copyright
feed.docs
feed.managingEditor
feed.rating
feed.webMaster
feed.ttl
feed.dc

RssItem item = feed.items.first;
item.title
item.description
item.link
item.categories
item.guid
item.pubDate
item.author
item.comments
item.source
item.media
item.enclosure
item.dc
```

**Atom**
```
feed.id
feed.title
feed.updated
feed.items
feed.links
feed.authors
feed.contributors
feed.categories
feed.generator
feed.icon
feed.logo
feed.rights
feed.subtitle

AtomItem item = feed.items.first;
item.id
item.title
item.updated
item.authors
item.links
item.categories
item.contributors
item.source
item.published
item.content
item.summary
item.rights
item.media
```

## License

WebFeed is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
