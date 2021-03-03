---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["first"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Desc Text."

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page

---