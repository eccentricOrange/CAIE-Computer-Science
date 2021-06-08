---
nav_order: 1
---

# Tools of the programming trade

Often, computer science courses teach you the theory of computing, programming, and all sorts of advanced topics. However, I've noticed a lack of resources that tell you how to actually tackle an IDE, how to keep track of your code, where to seek help et cetera.

If you're learning programming or computer science, these are some things you should consider using or exploring. If you want to learn these tools in detail, I would also recommend exploring the [Missing Semester](https://missing.csail.mit.edu/) from [MIT CSAIL](https://www.csail.mit.edu/).

## A command line
```bash
$ echo "Hello World"
$ sudo reboot
```
Contrary to what you might expect, command lines interfaces (CLIs) are quite fun to use. They let you do stuff quickly, interact with settings deep in a computer, or install stuff without going through a clunky installer. If you decide to pursue programming, you will eventually find them indispensable. Which CLI you use heavily depends on your computer's operating system (it is possible to install different terminals on most computers, but this is somewhat "advanced").

The gold-standard of CLIs are UNIX-like, i.e., they are similar to the CLI used by the [UNIX](https://simple.wikipedia.org/wiki/UNIX) OS. Linux-based operating systems and MacOS use this kind of a CLI. Although system traditionally used by Windows is the Command Prompt, Microsoft introduced PowerShell in 2014 and it supports some UNIX-like commands—I would recommend using PowerShell. You can run all Command Prompt commands in PowerShell but not vice-versa.

Getting started:
* [UNIX-like terminals](https://medium.com/@grace.m.nolan/terminal-for-beginners-e492ba10902a)
* [Command Prompt](https://www.makeuseof.com/tag/a-beginners-guide-to-the-windows-command-line/)
* [Linux Terminals](https://ubuntu.com/tutorials/command-line-for-beginners).

## Asking for help
You will frequently need to ask for help. While the variety online is infinite, there are three kinds of resources in general: forums, tutorials, and references. When you are stuck, try to just search on a search engine, like Google. Often you'll find something from one of these three resources.

### Forums
There are many to pick from, but [StackOverflow](https://stackoverflow.com/), part of the [StackExchange](https://stackexchange.com/) forums, is one of the best known forums for programming. If you have a question, chances are that some one would have asked it here, and more often than not, it would be answered.

I also like to use [Reddit](https://reddit.com), but you need to know the right subreddits to use. In general, [r/learnprogramming](https://www.reddit.com/r/learnprogramming) is good, though they do have a [list](https://www.reddit.com/r/learnprogramming/wiki/index#wiki_related_communities) of related ones.

If you use a specific platform like [Raspberry Pi](https://www.raspberrypi.org/forums/) or [Arduino](https://forum.arduino.cc/), their official forums are also good.

### Tutorials
If you need to learn how to do something, it's best to follow a tutorial. In general, try to look for a result from a reputable source like the official website, official documentation from somthing like [readthedocs.io](https://readthedocs.io/), or a well-known YouTube channel.

### References
Since so much of programming involves specific syntax, references exist for most platforms. These are usually lists of commands or functions, along with parameters and brief description. It's normal to keep referring very frequently.

## Source control
In programming, it is common to keep going back and forth with file versions, keep multiple variants/versions, or share code with collaborators and the open-source community. Managing it is messy.

Fortunately, **version control systems** exist.
> In software engineering, version control is a class of systems responsible for managing changes to computer programs, documents, large web sites, or other collections of information. Version control is a component of software configuration management ([Wikipedia](https://en.wikipedia.org/wiki/Version_control)).

The most widely used version control system is called [Git](https://git-scm.com/). It is lightweight, fast, easy to get started with, and has a ton of support form some of the largest organizations, like Microsoft. [GitHub](https://github.com/) is a popular website for uploading and sharing projects tracked using Git. Together, Git and GitHub also make it very easy to share code, get feedback, use others' contributions, and so on.

Getting started sources:
* Vidoes/playlists: [TheNetNinja](https://youtube.com/playlist?list=PL4cUxeGkcC9goXbgTDQ0n_4TBzOO0ocPR) (this is what I used when I learnt Git)
* Articles: [GitHub](https://docs.github.com/en/github/getting-started-with-github), [Git-SCM](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)