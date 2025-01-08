# sewing

[![Website](https://github.com/polarweasel/sewing/actions/workflows/cicd-website.yaml/badge.svg?branch=hugo-setup)](https://github.com/polarweasel/sewing/actions/workflows/cicd-website.yaml)

This repo generates (or rather, is about to) the main site at [polarweasel.org](https://polarweasel.org/) using a static site generator ([Hugo](https://gohugo.io)).

## How's it work?

The basic (human) workflow is: edit markdown, run Hugo to make sure it's happy, commit, push. Then, GitHub takes over: first, building the site with Hugo, and then using rsync to send only changed files to the web host.

There are some interesting details, like the web host's SSH credentials are kept as an encrypted secret in the repository. On the web host end, the credentials that GitHub uses to send the files are restricted to only the directory that serves the site.

### Hugo tidbits

Run the live-reload server: `hugo server -D --disableFastRender`

Build the site: `hugo` (or `hugo -s sewing-info/` from the root of the repository, as the pipeline does)

## License

This repo is licensed under the **CC BY-NC-SA 4.0** license. For more details, read the Creative Commons [description of the CC BY-NC-SA 4.0 license](https://creativecommons.org/licenses/by-nc-sa/4.0/).
