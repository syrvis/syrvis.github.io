# syrvis.github.io

The source of the Syrvis website, served at [syrvis.github.io](https://syrvis.github.io/). Syrvis runs your own services on a Synology NAS from one document that declares them, and it gives you four ways to manage the server: the `syrvis` command on your computer, a console in your browser, an AI agent through its MCP bridge, and an OpenTofu provider.

The site holds the user guide, which takes you from the install to your first services, the design pages, which describe each component, and the provability pages, which say what the TLA+ models check.

## What is here

| path | what it is |
|---|---|
| `index.html` | the home page |
| `guide/` | the user guide |
| `design/` | the design pages |
| `provability/` | the provability pages |
| `_layouts/`, `_includes/`, `assets/`, `images/` | the page layout, its parts, the stylesheet and the pictures |
| `_config.yml` | the Jekyll settings GitHub Pages builds the site with |
| `scripts/hygiene`, `scripts/hygiene-gate` | the scan that keeps private names out of the published files |

GitHub Pages builds the repository's root with Jekyll and its `jekyll-relative-links` plugin, so a page links to another by its `.md` file and every link stays relative.

## Check a change

```
make check
```

It needs git, shasum and `/usr/bin/python3`. It confirms the scanner matches its pinned sum, runs the hygiene scan with every group judged, and refuses an em-dash in a page. A pull request needs it green.

## The organisation's repositories

| repository | what it holds |
|---|---|
| [syrvis](https://github.com/syrvis/syrvis) | the daemon on your server, its DSM packages, its API and the OpenTofu provider |
| [syrvis-cli](https://github.com/syrvis/syrvis-cli) | the `syrvis` command for your computer |
| [syrvis-client](https://github.com/syrvis/syrvis-client) | the Go library a program embeds to talk to the daemon |
| [syrvis-console](https://github.com/syrvis/syrvis-console) | the console in your browser |
| [syrvis-workflow](https://github.com/syrvis/syrvis-workflow) | the workflow engine |
| [syrvis-deploy](https://github.com/syrvis/syrvis-deploy) | the deployment service |
| [syrvis-mtls](https://github.com/syrvis/syrvis-mtls) | the mutual TLS transport |
| [syrvis-common](https://github.com/syrvis/syrvis-common) | the shared layers beneath the services |
| [.github](https://github.com/syrvis/.github) | the organisation's front page on GitHub, and its security and contributing policies |

## Reporting

A mistake in a page: open an issue [here](https://github.com/syrvis/syrvis.github.io/issues). A bug in Syrvis: the organisation's [contributing guide](https://github.com/syrvis/.github/blob/main/CONTRIBUTING.md) says which repository takes it. A security problem: follow the organisation's [security policy](https://github.com/syrvis/.github/blob/main/SECURITY.md), never an issue.

MIT licensed; see `LICENSE`.
