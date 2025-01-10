---
title: Welcome to the FlowWest Knowledge Base
---

This site hosts documentation, guides, and other technical writings by the FlowWest Data team.

## Creating new content

To create new content, follow these steps.

1. Clone repo onto your machine.
2. Create a new branch, its a good idea to name the branch after the title of your article.
3. Create a new markdown file (.md) in the content/ folder with this frontmatter:

```yaml
---
title: Your Title Here
date: YYYY-MM-DD
draft: true
tags: [relevant, tags, here]
---
```

4. Use npm or another Markdown preview to preview your draft as you develop, see the section below on installing npm
and quartz if you want to use node to preview your content (recommended).
5. Once complete change draft from `true` to `false` and make a PR into branch `v4`, your content will be published once approved and merged.


### Install Node and set up quartz
To install node follow the instructions [here](https://github.com/nvm-sh/nvm) for MacOS and Linux, and [here](https://github.com/coreybutler/nvm-windows) for Windows. Once done you can install quartz with

```bash
# must be within the Knowledge base repo
npm i
```

and you can setup a preview of the site (and your markdown) with:

```bash
npx quartz build --serve
```


