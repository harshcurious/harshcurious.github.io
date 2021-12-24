---
title: "Today I Learnt 2"
date: 2021-03-31T11:26:01+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["TIL"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: true
description: "Notes on what I learnt on March 31, 2021."

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

---

## [Awesome Browser Addons](https://youtu.be/N66CmWhgrO4)

Learnt about some new and interesting Firefox addons (probably available for other browsers).

- Violent Monkey : Kinda like greasemonkey or tampermonkey. [Open source](https://violentmonkey.github.io/). Let's you run userscripts (basically Javascript assets) to change functionality on a website. It is getting updated regularly on [github](https://github.com/violentmonkey/violentmonkey).
- [LocalCDN](https://www.localcdn.org/) : This could be rather interesting especially if I can do it on my pi hole. For now I have added it to Brave via the unofficial build for chromium browsers. Some [incompatibilities exist](https://codeberg.org/nobody/LocalCDN/wiki/Home#user-content-2-can-i-use-this-extension-in-my-chrome-browser). Maybe I will add it to Firefox too.
- [Sponsorblock](https://github.com/ajayyy/SponsorBlock) : This is cool. It blocks the mid roll ads for various creators. The sponsor timestamps are crowd-sourced. Interesting over all, but I am never going to use it.
- search by image: Can reverse search any image using various search engines.
- [DownThemAll](https://www.downthemall.net/) : Hasn't been updated since Nov. 2019. Is it eve working anymore?
- [Universal bypass](https://universal-bypass.org/) : Allows you to bypass the link shortners. Don't encounter them that often. I won't be using it.

A Side note about Brave. it has this interesting option to permit extensions to read and write site data when clicked. So now I don't have to allow my password manager to read all my site data. Good privacy bonus.

## [Armv9 Architecture announced](https://youtu.be/1kH1kJa9XJA)

- New version of ARM architecture announced. Added support for more ML architecture.
- Armv8 is the standard used everywhere: Android, iPhone, etc.
- Armv6 in the first iPhone, feature phones, Raspberry PI zero.
- These generational changes don't happen very often.
- Armv7 added conditional floating points, virtualization etc.
- Armv8 moved to 64 bits.
- Armv9 will probably be the standard for the next 10 years.
- Scalable Vector Extensions (SVE) : Vector based compute that enables better output per watt. Introduced in Armv8.
- SVE2 : Improvements in SVE. In Armv9.
- Hardware-level security improvements
  - Memory padding to prevent memory leakage.
  - Realm : Hardware level containers.
- Mediatek : Selling commercial chips in 2022 based on Armv9.
- Mid-year announcements of new A-cpu architectural designs every year by ARM.
- Expect three new chips. Successors to : X1, A78, and A55. Based on Armv9. All chips need same architectural level.
- Apple has been quick to adopt to new architectural changes in ARM design. First to use Armv7 (64 bits).
- The much speculated A15 bionic might be Armv9 chip.

### [From the horse's mouth](https://www.arm.com/company/news/2021/03/arms-answer-to-the-future-of-ai-armv9-architecture)

- Expects 100% of *shared data* to be processed on ARM (that includes the server space).
- Security:
  - Armv9 introduces the Arm Confidential Compute Architecture (**CCA**). This protects portion of code and data from read or write while-in-use at the hardware level.
  - **Realms**: Dynamically created regions that are separated from everything else while it is in-use, at rest, and in transit. Can be created by any application.
- AI :
  - SVE (in partnership with Fujitsu)
  - SVE2 enables better machine learning (ML) and Digital Signal Processing (DSP) capabilities. Improves
    - 5G processing
    - VR and AR
    - Local ML processing like image processing and smart home applications
    - Future aim to improve matrix multiplication within the CPU.
    - AI innovations in Mali GPU and Ethos NPU.
- Expect performance increase of over 30% across the next two generations.
- [*Total compute design*](https://www.arm.com/why-arm/total-compute) will improve specialized performance.
- Working on increasing frequency, bandwidth, and cache-size, and reducing memory latency.
- TODO : Want to read Total SoC Compute for Dummies, available at [ARM website](https://armkeil.blob.core.windows.net/developer/Files/pdf/dummies-guide/arm-total-soc-dummies.pdf).
- TODO : There is more about SVE [here](https://developer.arm.com/tools-and-software/server-and-hpc/compile/arm-instruction-emulator/resources/tutorials/sve).

### [From xda-developers](https://www.xda-developers.com/armv9-architecture/)

- First major revision since October 2011 when v8 was launched.
- There have been some revisions since.
- Major additions:
  - SVE2
  - Realm Management Extension (RME)
  - BRBE
  - Embedded Trace Extension (ETE) and Trace Buffer Extension (TRBE)
  - TME
- Anandtech article has been referenced for everything so let me move there.

### [From Anandtech](https://www.anandtech.com/show/16584/arm-announces-armv9-architecture)

- The arm versioning is about Instruction Set Architecture (ISA).
- Announced as part of the Arm's Vision Day event.
- v9 is not as big of a jump as v8 was. In v8 AArch64 was introduced, which was a new instruction set and execution mode.
- AArch64 is still the basis of V9.
- SVE2 is now replacing NEON.
- SVE based on NEON was used in Fujitsu's A64FX CPU core. Focused on high performance computing (HPC) applications.
- SVE2 also includes variable vector size. Also software to scale easily between IoT devices and future high powered cores.

## [Breaking the Cycle of Overthinking](https://youtu.be/lUxU6KnjNNs)

- Hyper-vigilant : Really aware of the surroundings. Constantly looking for escapes. Always looking for reasons to not be there. Trying to predict how other people see me. How I am offending them.

## Industry S01E02

- It has fairly negative representation of the finance industry.
- Shows work-pressure, stress, use of drugs, hostile workplace environment and sexual misconduct.
- Shows them in the real-life messy style.
- Hard to say if these things happen with the frequency displayed.
- Has the classical drama stuff.
- HR is all about PR.

## Added support for MathJax and Plotpy on this website

### The mathjax support

- Followed the instruction from <https://geoffruddock.com/math-typesetting-in-hugo/> with minor additions.

1. Create a file called `mathjax_support.html` in the folder `./layout/partials` with the following content:

  ```html
  <script>
  MathJax = {
    tex: {
      inlineMath: [['$', '$'], ['\\(', '\\)']],
      displayMath: [['$$','$$'], ['\\[', '\\]']],
      processEscapes: true,
      processEnvironments: true
    },
    options: {
      skipHtmlTags: ['script', 'noscript', 'style', 'textarea', 'pre']
      }
    };

    window.addEventListener('load', (event) => {
      document.querySelectorAll("mjx-container").forEach(function(x){
        x.parentElement.classList += 'has-jax'})
    });

  </script>
  <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
  <script type="text/javascript" id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
  ```

  I would not recommend creating it inside the theme folder, if you are ever planning on updating your theme.

2. Next if your theme has `header-extend.html` use that, if not then use the `header.html` file. It should be in the `./themes/THEME_NAME/layouts/partials`. Copy this file to your root directory keeping the same directory structure. So in my case my new file will be `./layouts/partials/header-extend.html` To this I add

```html
{{ if .Params.mathjax }}
{{ partial "mathjax_support.html" . }}
{{ end }}
```

If you are using the `head` file, ensure that this is added before the closing `</head>` tag.
3. Now if you have the statement `mathjax: true` in the front matter of your markdown file, then you can use mathjax on your website.
4. (Optional) To your archetype file, add the `mathjax: true` Front Matter.
5. (Optional) To your css file add:

```css
code.has-jax {
    -webkit-font-smoothing: antialiased;
    background: inherit !important;
    border: none !important;
    font-size: 100%;
}
```

### Plotly

- Used for creating interactive diagrams.
- Export your plot as a `json` file using the `write_image` library as follows:

```python
from plotly.io import write_image
#... Generate the fig here.
fig.write_json("plot_name.json")
```

- Add the following Hugo shortcode to `plotly.html` at `./layouts/partials/` :

```html
{{ $json := .Get "json" }}
{{ $height := .Get "height" | default "200px" }}
<div id="{{$json}}" class="plotly" style="height:{{$height}}"></div>
<script>
Plotly.d3.json({{$json}}, function(err, fig) {
    Plotly.plot('{{$json}}', fig.data, fig.layout, {responsive: true});
});
</script>
```

- Add this to your `header.html` or `header-extend.html` (as used for mathjax above).

```html
{{ if .Params.plotly }}
    <script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
{{ end }}
```

- Now if you have the statement `plotly: true` in the front matter of your markdown file, then you can use plotly on your website. by calling the shortcode as follows:

```
{{/*< plotly json="/plotly/plotly-hugo/scatter3d.json" height="400px" >*/}}
```

## Back to using Anki

- Have used it in the past. But it didn't have native MathJax support back then.
- Was overwhelmed the last time around.
- No app on the home screen. Won't worry about the counter
- TODO: Add the python commands over there.
- Added MiKelTeX to the environment, by searching for the term `environment variable` in the start menu. That made LateX on Anki work for me.
