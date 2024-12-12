---
layout: default
title: Open Source Compliance - Glossary
permalink: /glossary/
---


# Existing glossaries

* [TheFLOSSary](https://www.creative-destruction.org/project/theflossary/) - the repo is not public anymore. Here is a fork [TheFLOSSary](https://github.com/hesa/TheFLOSSary)

# Our own glossary

Table of content
* [C](#osc-c)
* [L](#osc-l)
* [R](#osc-r)
* [T](#osc-t)

<a id='osc-c'></a>
## C

### Compatibility (License compatibility)

License A is compatible with license B if the terms of the licenses do not conflict.

In practice you typically end up in a situation like this:
* You have a program, P, that you would like to distribute under the Apache-2.0 license, i.e. outbound license is Apache-2.0
* Your program uses the library M, which is licensed under MIT, i.e. MIT is the inbound license

This means you will be asking the question: ***Can I use component M in my program P?***

This question can be answered by using Open Source Compliance <a href="#osc-resources">resources</a> and <a href="#osc-tools">tools</a>. 

<a id='osc-r'></a>
## R

<a id='osc-resources'></a>
### Resource (Open Source Compliance resource)

A resource with data that can be used to solve specific compliance problem. The resource can be in different forms, including web site, JSON file or a FAQ.

Examples:

* OSADL's [license matrix](https://www.osadl.org/fileadmin/checklists/matrix.json), part of [OSADL's license checklist](https://www.osadl.org/Access-to-raw-data.oss-compliance-raw-data-access.0.html). The matrix contains data with compatibility status between two licenses.

* Open Source Software Data Analytics Lab@PKU-SEI's [license matrix](https://github.com/osslab-pku/RecLicense/blob/master/knowledge_base/files%20for%20program%20input/compatibility_63.csv), part of [RecLicense](https://github.com/osslab-pku/RecLicense). The matrix contains data with compatibility status between two licenses.

More resources can be found here: <a href="/tooling-resources/">Tooling and resources</a>

<a id='osc-t'></a>
## T

<a id='osc-tool'></a>
### Tools (Open Source Compliance tool)

A software solving a specific compliance problem. The software can be in different forms, including web ui, command line program and module/library.

Examples:

* [ScanCode](https://github.com/aboutcode-org/scancode-toolkit/) - ScanCode detects licenses, copyrights, dependencies by "scanning code"

* [flict](https://github.com/vinland-technology/flict) -  Flict checks compatibility between licenses and also for projects.

More tools can be found here: <a href="/tooling-resources/">Tooling and resources</a>



