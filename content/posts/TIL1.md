---
title: "Today I Learnt 1"
date: 2021-03-25T19:46:43+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["youtube", "notes", "bullshit", "coronavirus", "codium", "vscode", "TIL"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Taking stock of what I learned on March 26th, 2021."

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: false
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page

---
## The second wave of coronavirus is here in India

I read [this article](https://indianexpress.com/article/india/delhi-first-time-since-november-daily-cases-surge-past-50000-in-24-hours-7245603/) from indian express in the morning. The daily cases yesterday were over 50000 for the first time since November. There are reported cases of multiple new variants ([in a situation were DNA sequencing is extremely rare](https://science.thewire.in/health/insacog-ccmb-igib-novel-coronavirus-variants-genome-sequencing-covid-19-surge/)).

The situation is frightening, especially some of the new variants being able to evade the immune system much more efficiently. I have been wearing a mask in public spaces at all times, but nobody else seems to be interested in doing so. Still the vast majority of people I encounter on my daily walk don't wear a mask.

## Bullshitting the bullshitter

- From the horse's mouth: talk with [Shane Littrell](https://uwaterloo.ca/reasoning-decision-making-lab/people-profiles/shane-littrell) on the [Guardian science podcast](https://www.theguardian.com/science/audio/2021/mar/25/you-cant-bullshit-a-bullshitter-or-can-you-podcast).
- [The research paper: ‘You can’t bullshit a bullshitter’ (or can you?):Bullshitting frequency predicts receptivity to various types of misleading information](https://doi.org/10.1111/bjso.12447). Open access :unlock:
- From the abstract:
  - Research into both receptivity to falling for bullshit and the propensity to produce it.
  - Truism: You can't bullshit a bullshitter. But is it true?
  - Both bullshit receptivity and bullshitting frequency are negatively related to cognitive ability and aspects of analytic thinking style (Littrell, Risko, & Fugelsang, 2021; Pennycook, Cheyne, Barr, Koehler, &Fugelsang, 2015).
  - However, separate research suggests that individuals who frequently engage in deception are better at detecting it
    - people who self-report engaging more frequent ly in lying (i.e., deliberately convincing someone of a falsehood)also self-report being signiﬁcantly better than average at detecting lies from others (Zvi &Elaad, 2018).
    - those who produce more convincing lies are also actually better at detecting lies (W right, Berry, & Bird, 2012, 2013)
    - other more recent studies suggest this may not be the case (Hudson, Vrij,Akehurst, Hope, & Satchell, 2020).
  - Found that frequency of persuasive bullshitting (i.e., bullshitting intended to impress or persuade others) positively predicts susceptibility to various types of misleading information and that this association is robust to individual differences in cognitive ability and analytic cognitive style.
  - N=826; across three studies.
- Recent research has suggested that bullshitting and lying, while clearly related, are psychologically distinguishable constructs (Littrell, Risko, et al., 2021).
- Liars show a stronger negative association with self-regard and a stronger positive association with lie acceptability than bullshitters (Littrell, Risko, et al., 2021).
- **Persuasive bullshitting** (i.e., bullshitting motivated by a desire to impress or persuade others) has been found to be signiﬁcantly, negatively related to cognitive ability while it's not the case with lying (Littrell, Risko, et al., 2021; Michels, Molz, & Maas genannt Bermpohl, 2020).
- **Bullshit**: information designed to impress, persuade, and/or otherwise mislead that is often constructed with an indifference for the truth. Bullshit can range from coherent yet hyperbolic (any article headline from Atlantic) or suspiciously implausible (almost all conspiracy theories), to jargon-heavy yet obscure or non-sensible (a-la [Deepak Chopra](https://sebpearce.com/bullshit/)), to technically accurate yet misleadingly irrelevant (a lot of climate deniers; gun right advocates; mann-ki-baat).
- Bullshitting is **intentional**.
- The extent to which a person intentionally spreads bullshit (i.e.,engages in bullshitting) in everyday situations can be estimated using the *Bullshitting Frequency Scale* (BSF; Littrell, Risko, et al., 2021).
- BSF measures self-reported frequency with which people bullshit to:
  - impress, persuade, or ﬁt in with others (persuasive bullshitting)
  - be evasive (evasive bullshitting) for example politicians.
- *Persuasive bullshitting frequency* is positively related to 'bullshitting behavior' like claiming expertise in non-existent topics (Jerrim et al., 2019) and negatively related to intelligence and some aspects of analytical thinking.
- Basically evasive bullshitting is useful like lying to a partner about an awful haircut. It can definitely be useful in forming coalition. Eg: recent Sharad Pawar comments.
- I am more interested in bullshit receptivity. I kinda appreciate the ability to bullshit. I have a tough time doing that. I am a lot straightforward. It is socially useful to fit in, especially the evasive kind.
- **Bullshit receptivity**: the ease with which someone fall for bullshit.
- *Bullshit receptivity scale* (Pennycook et al. 2015):

## Setup for VSCodium

- I had an installation for VSCodium in my machine, but I hadn't used it ever. I decided to use it.
- Took a while to set it up.
- Primarily, there are a few issues with using codium instead of code.
  - I couldn't figure out how to install some of the extension I wanted. They weren't available on the default extension store. [Apparently](https://github.com/VSCodium/vscodium/blob/master/DOCS.md#extensions-marketplace) codium uses [open-vsx.org](https://open-vsx.org/) as extension gallery. So only the extensions registered there are available on codium. There is a workaround to use the VS Code Marketplace, but it may not be [legal](https://github.com/microsoft/vscode/issues/31168). From the VSCodium Doc:
  Create a custom `product.json` at `%USER%\AppData\Roaming\VSCodium` with the following content:

    ```json
    {
     "extensionsGallery": {
        "serviceUrl": "https://marketplace.visualstudio.com/_apis/public/gallery",
        "cacheUrl": "https://vscode.blob.core.windows.net/gallery/index",
        "itemUrl": "https://marketplace.visualstudio.com/items",
        "controlUrl": "",
        "recommendationsUrl": ""
      }
    }
    ```

    Use this at your own risk.
  - Another important aspect is the [propriety debugging tools for C#/C++](https://github.com/VSCodium/vscodium/blob/master/DOCS.md#proprietary-debugging-tools). This was especially concerning for me because I plan on using [PlatfomIO IDE](https://platformio.org/) for Raspberry Pi Pico. And PlatformIO is built on the C++ extension. For now I have used the vsix installation for these two.
  - I have still not managed to get the git Oauth working on codium. I just keeps failing to login. *Update 27th Match*: Finally managed to fix it. Here is what I did.
    - Just click on the login option on codium. It should open a link in the browser which would look something like this:
      > https://vscode-auth.github.com/authorize/?callbackUri=**vscodium**://vscode.github-authentication/did-authenticate%253FwindowId%253D1&scope=read:user%20repo%20user:email&state=16b13b86-dbca-4b0d-ac5e-d5c1def0f748&responseType=code&authServer=https://github.com
    - Don't click on the continue button.
      ![Don't click yet](/static/TIL/1/codiumgithub.png)
    - Instead edit the url just after `callbackUri=` from `vscodium` to `vscode`. So the new link should be:
      > https://vscode-auth.github.com/authorize/?callbackUri=**vscode**://vscode.github-authentication/did-authenticate%253FwindowId%253D1&scope=read:user%20repo%20user:email&state=16b13b86-dbca-4b0d-ac5e-d5c1def0f748&responseType=code&authServer=https://github.com
    - Now you are ready. Click on the continue button. You shouldn't get an error. Instead you will get to the authorization page. Fill your details.
    - Once you have authorized the extension, you should get to a page which gives you a token and a open in app link. The open in app link will not work. Instead copy the token.
    - Go back to the codium window. At the bottom, in the status bar, you will see a github.com button. Click it. The command running utility opens. In it paste your token and press enter. If you press Esc, you will have to restart the authentication process.
    - This worked for me, your milage may vary.
  - I have added a bunch of extensions. I am syncing them using my github account via gists. There is an extension called [Settings Sync](https://open-vsx.org/extension/Shan/code-settings-sync). It can sync your settings using a secret *gist*.

## Watched a fair bit of the cricket match 🏏

I don't know what is happening. Sometimes I think the sheer number of good players in the Indian team is too much and sometimes I feel like England has a more well rounded team than India. I don't know if both can be true at the same time. England crushed India in a more difficult run chase than the 1st ODI. I don't know what to think anymore. I was utterly surprized at how India won the the t20 series and the first ODI. Maybe it was a fluke. I have to look at some kind of data. The matches so far in the limited over games have been fun but confusing.
