---
nav_order: 7
---

# Tips and tricks

<script async>
window.MathJax = {tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]},svg: {fontCache: 'global'},jax: ["input/TeX", "output/CommonHTML"]};(function () {var script = document.createElement('script');script.src = 'https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js';script.async = true;document.head.appendChild(script);})();
</script>

I often find myself wanting to discuss little tips, tricks, and other ideas, but they don't merit a full article. So I'll keep posting them here. Each tip has a number and the date when I first wrote it in the format `XXX-DD-MM-YYYY` (where `XXX` is the number), so that it can easily be found later.

**Note:** There is no defined release schedule for these tips.

## 001-09-10-2021
### Foo, Bar, and Baz
If you decide to look for help online, especially on a forum full of professional programmers (such as Stack Overflow), you might find these three words — among others — thrown around a lot.

They are [metasyntactic variables](https://en.wikipedia.org/wiki/Metasyntactic_variable), arbitrary variables used as placeholders. There is no specific meaning behind them, much like how $x$, $y$, $t$ etc are used to define other expressions in mathematics.

Further reading:
* [Foobar \(Wikipedia\)](https://en.wikipedia.org/wiki/Foobar)
* [Meaning of foo, bar, baz, etc \(Stack Overflow\)](https://stackoverflow.com/questions/34212049/meaning-of-foo-bar-baz-etc)


## 002-17-10-2021
### Dealing with theoretical papers
Well, the only advice I have is kinda generic, but it helped a me lot. This was my Achilles' heel too.

1. Try to convert the material from a list of points to something hands-on. For an example with printers, I took apart an old inkjet printer and spent about a week trying to put it back together. So upon reading the books, it felt "obvious". For other types, my (amazing) teacher dug up YT videos by HP, Epson, and Xerox. They explained the working in such depth that the textbook again felt "obvious".

2. For the remainder, like lists of advantages and disadvantages, I just used traditional study methods where I couldn't answer by reasoning. Read, practice, and do lots of papers. Sorry, I don't have any better ideas.

## 003-17-10-2021
### What do do when a bit of code is confusing?
You'll often run into a situation where a bit of code is confusing. For example, look at this bit of Python code.

```python
x = 5
x = x + 1
print(x)
```

Depending on your experience with programming, the line `x = x + 1` may be either daunting or completely obvious. How can something be equal to one greater than itself?

![Spongebob based meme](https://i.imgur.com/XydhvcK.png)

Nevertheless, if you're ever confused with something like this, there is always one thing which can sort it out: **convert it to something like assemble language**.

The above example would break down like this:

```
LOAD the value from location x into memory
INCREMENT the value in memory
STORE the value from memory into the location x
```

This makes it obvious that `x = x + 1` is an assignment statement, and you immediately understand that it should not be seen as a mathematical expression.

## 004-17-10-2021
### Trace tables

I'll take paper 0478/22/M/J/20 as an example, and we can look at **question 4**.

The first thing you want to do is to understand what the algorithm is even saying. Just looking at the flowchart, we can see some notion of a loop (since an starting arrow from a decision box leads back to one step above it). Next, we can see that there appear to be some actions that may be taken if we went ahead with the loop (instead of ending).

With that, now take help of the information provided above the question. Apparently, this algorithm decides whether a player moves up, down, or stays where they were.

Now that you know this, it's easy to figure out what's going on. If you gain more than you lose, you move up a level; if you lose more, you move down; if your net gain/loss is 0 you stay where you were; and once you enter -1 for `PointsWon`, it ends
Now if you're given two numbers (one for each of `PointsWon` and `PointsLost`), you can figure out what the output of the program will be. That's essentially one iteration of the loop
And that's all you need for a trace table—one row is one iteration.

So take the first two numbers from the data given to you in part **4(a)**, write them in the `PointsWon` and `PointsLost` columns of the first row, calculate their difference in the third column, and in the fourth column, write what happens to the player (they move up, down, or keep trying).

Then move on to the next pair of numbers and the next row
The only catch is that once you see `PointsWon = -1`, you do not calculate a difference or output anything, because the algorithm ends. So leave those two cells blank.

So what's the broad method here? Try to figure out what the algorithm is trying to do. As another example, if I just gave you steps that ask you to:.

1. Boil water
2. Turn off the heat
3. Add leaves
4. Wait for 4 minutes
5. Pass the mixture through a metal mesh into a tumbler
6. Add sugar
7. Add milk
8. Stir

...it might be bit confusing. But if I just told you to make tea, you'd get what I'm trying to say.

<br> <br> <br>

[Visit this website's repo](https://github.com/eccentricOrange/CAIE-Computer-Science){: .btn .btn-outline }
