---
title: 'JupyterLab Python Environments'
date: 2022-02-14T14:17:53+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ['Jupyter', 'JupyterLab', 'conda', 'environment']
author: 'Harsh Kumar'
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
# comments: true
description: 'Learning how to add a conda environment to JupyterLab'

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: false
# cover:
#   image: '<image path/url>' # image path/url
#   alt: '<alt text>' # alt text
#   caption: '<text>' # display caption under cover
#   relative: false # when using page bundles set this to true
#   hidden: true # only hide on current single page

plotly: false #turn plotly support on and off
mathjax: false #turn mathjax support on and off
---

## Adding Environments to JupyterLab

> Source: <https://janakiev.com/blog/jupyter-virtual-envs/>

1. Activate the environment: `conda activate my_env`
2. Install `ipykernel` in your environment. Using:
   - `pip install --user ipykernel`
   - `conda install -c conda-forge ipykernel`
3. Run the following to add the current kernel[^kernel] to jupyterlab installation in base environment:
   ```sh
   python -m ipykernel install --user --name=udemy-data-science
   ```

## Removing Environments from JupyterLab

- Check the list using:
  ```sh
  jupyter kernelspec list
  ```
- Remove a kernel using:
  ```sh
  jupyter kernelspec uninstall myenv
  ```

[^kernel]: So don't forget to activate the environment first.
