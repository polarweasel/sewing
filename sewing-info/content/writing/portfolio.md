---
title: Portfolio
type: default
draft: false
---

Here's a very basic portfolio. I've got other samples to share, and many stories, but this set has been useful lately, so here it is online for easier sharing.

I'm working primarily in SaaS these days, but have written for clients in television, GIS, finance, medical software, and consumer software, among others.

[**I'm polarweasel on GitHub**](https://github.com/polarweasel). All my work the last few years has been docs-as-code, hosted in public (Yugabyte, CableLabs) or private (PubNub) GitHub repositories.

* [**YugabyteDB docs contributor guide**](https://docs.yugabyte.com/preview/contribute/docs/) &mdash; Most of the docs I worked on at YB were collaborative efforts. The pages here, though, are mine, other than the page on syntax diagrams (everyone avoided that process like the plague).

* [**smart-tap.yaml**](/portfolio/smart-tap.yaml) is an OpenAPI spec for a CableLabs project. Copy and paste the text into [Smartbear's online editor](https://editor-next.swagger.io/) for a fairly nice preview.

  This is part of a larger industry specification for IoT devices on a cable TV network. These devices are switchable signal splitters that sit on the line and feed several houses at a time. My role included designing the middleware APIs and project-managing development of the overall spec.

* [**swagger-spec-template.yaml**](/portfolio/swagger-spec-template.yaml) is an OpenAPI 2.0 (Swagger) template I put together at Ericsson. Again, drop it into [Smartbear's online editor](https://editor-next.swagger.io/) for a nice preview.

  The goal here was to help developers and API designers unfamiliar with Swagger/OpenAPI get productive with their own designs as easily as possible.

* [**apispecs-README.md**](/portfolio/apispecs-README.md) is an early version of the README for Ericsson’s OpenAPI project. It references a build system I created that we ultimately scrapped in favour of a simpler approach, but I think it’s a good example of a useful overview document for new contributors.

* [**AlexBall-samples.pdf**](/portfolio/AlexBall-samples.pdf) contains excerpts from an assortment of documents:

  * **Pages 1-2** are from a C API reference, generated by Doxygen, targeted at hardware developers.
  * **Pages 3-4** are a bit higher-level documentation of message flows in a design document.
  * **Pages 5-6** are an API overview from the same design document. The purpose was not to serve as a developer’s guide, but rather as a “here’s what we implemented, so you can evaluate the code” document.
  * **Pages 7-8** describe how a cable set-top box loads its data for the on-screen guide. This particular device could not load and process guide data in the standard way due to significant hardware constraints, so the company had to devise a new mechanism for delivery and loading.
  * **Page 9** is part of a company’s application for federal approval of its electronic health records software. My contribution was to research and describe their approach to encryption and privacy. Almost nobody gets that federal approval the first time around; these folks did.
