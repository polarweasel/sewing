# API specs, built in Swagger (OpenAPI)

This is a project to help us figure out how to write and manage API specs written with the [OpenAPI](https://openapis.org/ "OpenAPI official site") specification, which is a project of the Linux Foundation. The [Swagger](http://swagger.io/ "Swagger project site") site has an overview of tools, process, and so on.

For C# development, we may want to look at [NSwag](https://github.com/NSwag/NSwag/wiki "NSwag project site"), as well.

**Timeline** We're in the early stages here, but do have working tooling. Still working on getting auto builds set up, and the website hosted somehow for internal use.

## Getting started

Clone or copy this repository so you can run things locally.

To begin creating a spec of your own, start with the [spec template](api-specs/full-swagger-spec-template.yaml). Copy the contents into the [online Swagger Editor](http://editor.swagger.io/) and explore how it's put together. Once you have a sense of how things work, and you've familiarized yourself with what's already in the APIs (use the web interface to do that), explore the [directory structure](#directory-structure) and [fragment structure](#fragment-structure).

Once you've created a valid spec, break out the paths (and object definitions and parameters, as necessary), and [submit your merge request](http://thor.mr.ericsson.se/ealxbal/api-spec-testing/merge_requests).

Refer to the [OpenAPI spec itself](http://swagger.io/specification/) as you're writing your API definitions; it's quite usefully-written, in most cases.

### Dependencies

* bash (for Windows, [Git-Bash](https://git-scm.com/downloads) works properly)
* [NPM](https://www.npmjs.com/) (Node Package Manager)
* NPM packages (`npm install <packagename> -g`):
  * http-server (helpful for local testing)
  * json-refs (parses local and remote #ref links in YAML and JSON files)

### Viewing the current docs

Clone (or copy) this repository. Then in bash, do this:

```bash
cd build
./build-everything
http-server ../site
```

Open a web browser and point it to your machine at [127.0.0.1:8080](http://127.0.0.1:8080/). That will show you the current documentation.

## Directory structure

**[/api-specs](api-specs)** holds the API spec documents themselves (in fragments; see [Fragment structure](#fragment-structure), below). Your additions go here.

**[/build](build)** holds the build scripts and intermediary build output files. Take a look at the [build-everything script](build/build-everything) (and the scripts it calls) to see how the concatenation and deployment works.

**[/site](site)** holds the HTML doc website itself, running on the [swagger-ui](https://github.com/swagger-api/swagger-ui) framework.

## Fragment structure

Each API spec is defined by 1-3 YAML fragment files:

* **Path** definitions ([/api-specs/paths](api-specs/paths)/SPECNAME-paths.yaml) are *required*. You define your API's endpoints and methods here.
* **Parameter** definitions ([/api-specs/parameters](api-specs/parameters)/SPECNAME-parameters.yaml) are *optional*. If your API defines new parameters, they go in a file specific to your API.
* **Object** definitions ([/api-specs/object-definitions.yaml](api-specs/object-definitions.yaml)) are *optional*. If your API defines new objects, they go in here. This file contains *all* the objects used by all of the APIs. The object definitions in this file should be arranged alphabetically.

[/build/all.yaml](build/all.yaml) is the skeleton file that references YAML fragments. Each fragment (paths, object definitions, and parameter definitions) gets built from fragments defined by each API spec.

[/build/build-everything](build/build-everything) is the master script that calls the other build scripts. The build process concatenates all of the YAML fragments, for all of the API specs, into a single OpenAPI spec file, then converts that into a JSON file. That [JSON file](site/swagger.json) feeds the HTML site.
