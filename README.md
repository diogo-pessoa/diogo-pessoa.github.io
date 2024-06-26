My personal Page
----

[![Deploy Hugo site to Pages](https://github.com/diogo-pessoa/diogo-pessoa.github.io/actions/workflows/hugo.yml/badge.svg)](https://github.com/diogo-pessoa/diogo-pessoa.github.io/actions/workflows/hugo.yml)

Source code for my personal page [diogo-pessoa.github.io](https://diogo-pessoa.github.io/)


## Development

### requirements

- hugo
- golang v1.22
- git v2.33.0
- node v16.11.1

To run the project locally, you need to have hugo installed. Then, run the following command:

```bash
hugo server 
```

#### Build with drafts

```bash
hugo server --buildDrafts

```

### Deployment

The deployment is done automatically by github actions. The action is triggered by a push to the main branch. The action will build the project and push the changes to the `gh-pages` branch.

### theme

The theme used in this project is [hugo-coder](https://github.com/luizdepra/hugo-coder.git)

## References:

[hugo quickstart](https://gohugo.io/getting-started/quick-start/)
