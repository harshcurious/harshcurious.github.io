---
title: 'Cleaning conda package cache'
date: 2022-02-14T14:27:52+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ['conda', 'cache']
author: 'Harsh Kumar'
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
# comments: true
description: "Learning how to clean conda cache. Don't forget to do this regularly"

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: false
# cover:
#     image: "<image path/url>" # image path/url
#     alt: "<alt text>" # alt text
#     caption: "<text>" # display caption under cover
#     relative: false # when using page bundles set this to true
#     hidden: true # only hide on current single page

plotly: false #turn plotly support on and off
mathjax: false #turn mathjax support on and off
---

> Source: <https://stackoverflow.com/questions/36308531/how-to-uninstall-all-unused-packages-in-a-conda-virtual-environment>

If you are anything like me you start multiple data science projects. To make things a little easier I make multiple conda environments. Conda does a decent job at reducing the space used my the packages[^symlinks]. But over time the conda folders can become boated. It's a good idea to do this regularly.

```conda
conda clean --yes --all
```

The `all` flag clears packages, and tarball used in the installation process.

You can also add a `dry-run` flag:

```conda
conda clean --all --dry-run
```

to check the size of unused packages. Can be quite large, if you have deleted/updated any conda environment!

[^symlink]: It creates symlinks to the same shared folder for all the environments.
