---
layout: default
title: Open Source Compliance - FAQ
permalink: /faq/
---

# FAQ

## License and Copyright scanners

### I 

## License databases

### I have a license name which is not recognised by my tooling

More and more often [SPDX identifiers](https://spdx.org/licenses) are used. Using these identifiers we can uniqely identify a license.

However when we look at the various ecosystems (maven, debian, pypi) we can see a lot of oddly named licenses, e.g. `GNU General Public License v2 (GPLv2)`

If you want to translate (normalize) a license name to a unique and known identifier you can use [FOSS Licenses](https://github.com/hesa/foss-licenses).

To use the Python command line program or the Python module, install foss-licenses: `pip install foss-flame`.

To normalize `GNU General Public License v2 (GPLv2)` with the command line program:
```
$ flame license "GNU General Public License v2 (GPLv2)"
GPL-2.0-only
```

To normalize the license using the Python module
```
>>> from flame.license_db import FossLicenses
>>> fl = FossLicenses()
>>> expression = fl.expression_license('GNU General Public License v2 (GPLv2)')
>>> print(expression['identified_license'])
GPL-2.0-only
```

## License compatibility

### How can I check if two licenses are compatible?

This questions requires a bit of context, such as
* use case - how you use the licensed component
* provisioning - how you provide the component to your user
* modification - if you have modified the component

Another thing to keep in mind is which license is inbound and which is outbound. Think about it this was:
* outbound license is the license you distribute your software under
* inbound license is the license of your component's dependency

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

Two licomp resources gave the answer `yes`. The other resources could not provide an answer, most likely because they did not support the provided context.