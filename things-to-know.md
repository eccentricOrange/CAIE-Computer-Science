---
nav_order: 6
---

# Tools of the programming trade

Often, computer science courses teach you the theory of computing, programming, and all sorts of advanced topics. However, I've noticed a lack of resources that tell you how to actually tackle an IDE, how to keep track of your code, where to seek help et cetera.

If you're learning programming or computer science, these are some things you should consider using or exploring. If you want to learn these tools in detail, I would also recommend exploring the [Missing Semester](https://missing.csail.mit.edu/) from [MIT CSAIL](https://www.csail.mit.edu/).

<br>

## A command line
```bash
$ echo "Hello World"
$ sudo apt-get moo
```
Contrary to what you might expect, command lines interfaces (CLIs) are quite fun to use. They let you do stuff quickly, interact with settings deep in a computer, or install stuff without going through a clunky installer. If you decide to pursue programming, you will eventually find them indispensable. Which CLI you use heavily depends on your computer's operating system (it is possible to install different terminals on most computers, but this is somewhat "advanced").

The gold-standard of CLIs are UNIX-like, i.e., they are similar to the CLI used by the [UNIX](https://simple.wikipedia.org/wiki/UNIX) OS. Linux-based operating systems and MacOS use this kind of a CLI. Although the system traditionally used by Windows is the Command Prompt, Microsoft introduced PowerShell in 2014 and it supports some UNIX-like commands, alongside its own scripting language. You can run all Command Prompt commands in PowerShell but not vice-versa.

Getting started:
* [UNIX-like terminals \(macOS\)](https://medium.com/@grace.m.nolan/terminal-for-beginners-e492ba10902a)
* [Command Prompt](https://www.makeuseof.com/tag/a-beginners-guide-to-the-windows-command-line/)
* [Linux Terminals](https://ubuntu.com/tutorials/command-line-for-beginners).

<br>

## Asking for help
You will frequently need to ask for help. When you are stuck, try to just look up the problem on a search engine, like Google. While the variety online is infinite, there are three kinds of resources in general: forums, tutorials, and references. Often you'll find something from one of these three resources.

If you have an error message or an error code, do search that too.

### Forums
There are many to pick from, but [StackOverflow](https://stackoverflow.com/), part of the [StackExchange](https://stackexchange.com/) forums, is one of the best known forums for programming. If you have a question, chances are that some one would have asked it here, and more often than not, it would be answered.

I also like to use [Reddit](https://reddit.com), but you need to know the right subreddits to use. In general, [r/learnprogramming](https://www.reddit.com/r/learnprogramming) is good, though they do have a [list](https://www.reddit.com/r/learnprogramming/wiki/index#wiki_related_communities) of related ones.

If you use a specific platform like [Raspberry Pi](https://www.raspberrypi.org/forums/) or [Arduino](https://forum.arduino.cc/), their official forums are also good.

**Best practices for forums:**
* [What have you tried?](https://mattgemmell.com/what-have-you-tried/)
* [How to ask a software question \(Wikipedia\)](https://en.wikipedia.org/wiki/Wikipedia:Reference_desk/How_to_ask_a_software_question)
* [Writing the perfect question](https://blogs.msmvps.com/jonskeet/2010/08/29/writing-the-perfect-question/)

### Tutorials
If you need to learn how to do something, it's best to follow a tutorial. In general, try to look for a result from a reputable source like the official website, official documentation from something like [readthedocs.io](https://readthedocs.io/), or a well-known YouTube channel.

### References
Since so much of programming involves specific syntax, references exist for most platforms. These are usually lists of commands or functions, along with parameters and a brief description. It's normal to keep referring very frequently.

<br>

## Source control
In programming, it is common to keep going back and forth with file versions, keep multiple variants/versions, or share code with collaborators and the open-source community. Managing it is messy.

Fortunately, **version control systems** exist.
> In software engineering, version control is a class of systems responsible for managing changes to computer programs, documents, large web sites, or other collections of information. Version control is a component of software configuration management ([Wikipedia](https://en.wikipedia.org/wiki/Version_control)).

The most widely used version control system is called [Git](https://git-scm.com/). It is lightweight, fast, easy to get started with, and has a ton of support form some of the largest organizations, like Microsoft, Google, and the Linux Foundation. [GitHub](https://github.com/) is a popular website for uploading and sharing projects tracked using Git. Together, Git and GitHub also make it easy to share code, get feedback, use others' contributions, and so on.

Getting started sources:
* Videos/playlists: [TheNetNinja](https://youtube.com/playlist?list=PL4cUxeGkcC9goXbgTDQ0n_4TBzOO0ocPR) (this is what I used when I learnt Git)
* Articles: [GitHub](https://docs.github.com/en/github/getting-started-with-github), [Git-SCM](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

<br>

## Using an IDE
If you're following some kind of a course, you will likely have heard the term [Integrated Development Environment \(IDE\)](https://simple.wikipedia.org/wiki/Integrated_development_environment). While you often get some kind of an editor when you install the software for a programming language (such as the [IDLE](https://docs.python.org/library/idle.html) for Python), a good IDE will make your coding experience significantly easier and more enjoyable.

Learn more:
* [CodeAcademy article](https://www.codecademy.com/articles/what-is-an-ide)
* [RedHat Article](https://www.redhat.com/en/topics/middleware/what-is-ide)

### Choosing an IDE or text editor
Many programmers [feel quite strongly](https://en.wikipedia.org/wiki/Editor_war) about their preference of IDEs and text editors. Following this culture, I would suggest you to research on your own—see what you like, read about the best IDEs for the languages you're using, and generally figure out what floats your boat.

After trying random software for a while, I've settled on the free [Visual Studio Code](https://code.visualstudio.com/) for the past couple of years. It's fast and stable, customizable yet easy to use, and allows editing in multiple languages. (not sponsored)

**StackOverflow Developer Survey 2019:** [click here](https://insights.stackoverflow.com/survey/2019/#development-environments-and-tools) to see a list of the most popular IDEs and editors in 2019. You can see the [most recent survey](https://insights.stackoverflow.com/survey/) too, but you'll have to dig out the section on environments.

![Real Programmers, xkcd 378](https://imgs.xkcd.com/comics/real_programmers.png)
[Real Programmers, comic 378 by xkcd](https://xkcd.com/378/)


<br> <br>

### A word of caution
While IDEs and text editors, CLIs, and Git are certainly helpful, they do have a little learning curve. If you're just getting started with programming, trying to learn to use all of them, **along with** trying to understand programming concepts and syntax, can be difficult and discouraging. Hence, I would advise you to first learn a language (using IDLE and Python, for example); or if you already know a language, learn to use an IDE before learning another language alongside. You might want to reserve CLIs and Git for later, when you'll need finer control and will have to handle more complex projects.

<br> <br> <br>

[Visit this website's repo](https://github.com/eccentricOrange/CAIE-Computer-Science){: .btn .btn-outline }
