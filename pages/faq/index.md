---
layout: default
title: Open Source Compliance - FAQ
permalink: /faq/
---

# FAQ

## License and Copyright scanners

## License databases

## License compatibility

### How can I check if two licenses are compatible?

This questions requires a bit of context, such as
* use case - how you use the licensed component
* provisioning - how you provide the component to your user
* modification - if you have modified the component

Another thing to keep in mind is which license is inbound and outbound. To make this easy, think about it this was:
* inbound license is the license of your component's dependency
* outbound license is the license you distribute your software under

So, how do we check if we can use a component under MIT in our software which we want to release under GPL-2.0-or-later?

***Using flict***
First of all, install [flict](https://github.com/vinland-technology/flict).

```
$ flict -of text verify -il MIT -ol GPL-2.0-or-later
Yes
```

*Note: flict does not, as of now, take into consideration the above context.*


***Using licomp-toolkit***
First of all, install [Licomp toolkit](https://github.com/hesa/licomp-toolkit).

Let's assume you:
* use the MIT component as a library
* provide your program by distributing it in binary format
* you do not modify the MIT component

```
$ licomp-toolkit -p binary-distribution -u library verify -il MIT -ol GPL-2.0-or-later  | jq .summary.results
{
  "nr_valid": "2",
  "yes": {
    "count": 2,
    "percent": 100.0
  }
}
```

Two licomp resources gave the answer `yes`.