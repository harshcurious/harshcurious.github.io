---
title: 'How to remove subfolders/subdirectories from git tracking'
date: 2021-12-25T10:00:42+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ['git']
author: 'Harsh Kumar'
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
# description: ''

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: false
cover:
  image: '<image path/url>' # image path/url
  alt: '<alt text>' # alt text
  caption: '<text>' # display caption under cover
  relative: false # when using page bundles set this to true
  hidden: true # only hide on current single page

plotly: false #turn plotly support on and off
mathjax: false #turn mathjax support on and off
---

> From <https://stackoverflow.com/questions/2545602/how-to-git-ignore-subfolders-subdirectories>

To ignore `Solutions/projects/bin/Debug` but not `bin/Debug`

```gitignore
Solution/*/bin/Debug
```

you can also use the \*\* wildcard to match any level of subdirectories:

```
**/bin/Debug/
```

## Bonus Content: Remove existing git tracked files

Now say you had a folder (commited to your git repository) that you now wanted to remove altogether from your repository. First add it to your gitignore file. Then do one of the following steps.

<https://stackoverflow.com/questions/7075923/resync-git-repo-with-new-gitignore-file>

1. Extreme

   ```
   git rm -r --cached
   git add .
   git commit -m "Updated .gitignore"
   ```

2. Controlled (didn't work for me last time around):
   ```
   git rm --cached `git ls-files -i --exclude-standard`
   ```
