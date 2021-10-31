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

This makes it obvious that `x = x + 1` is an assignment statement, you immediately understand that it should not be seen as a mathematical expression, and know that the program would print `6`.

## 004-17-10-2021
### Trace tables

I'll take paper `0478/22/M/J/20` as an example, and we can look at question **4**.

The first thing you want to do is to understand what the algorithm is even saying. Just looking at the flowchart, we can see some notion of a loop (since an starting arrow from a decision box leads back to one step above it). Next, we can see that there appear to be some actions that may be taken if we went ahead with the loop (instead of ending).

With that, now take help of the information provided above the question. Apparently, this algorithm decides whether a player moves up, down, or stays where they were.

Now that you know this, it's easy to figure out what's going on. If you gain more than you lose, you move up a level; if you lose more, you move down; if your net gain/loss is 0 you stay where you were; and once you enter -1 for `PointsWon`, it ends

Now if you're given two numbers (one for each of `PointsWon` and `PointsLost`), you can figure out what the output of the program will be. That's essentially one iteration of the loop. And that's all you need for a trace table—one row is one iteration.

So take the first two numbers from the data given to you in part **4 (a)**, write them in the `PointsWon` and `PointsLost` columns of the first row, calculate their difference in the third column, and in the fourth column, write what happens to the player (they move up, down, or keep trying).

Then move on to the next pair of numbers and the next row. The only catch is that once you see `PointsWon = -1`, you do not calculate a difference or output anything, because the algorithm ends. So leave those two cells blank.

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

## 005-19-10-2021
### Logic gate diagrams

I'll take question **5 (a)**, of the paper with paper code `0478/13/M/J/16`, as an example for explaining how to translate a logic statement into a logic diagram. You may find it helpful to try and draw your own circuit along my explanation (or look at the solution from the marking scheme if you're really stuck).

<br>

Recognise that there are two ways to represent logic operations (at the level of IGCSE). The first is a statement, and the second is a diagram. You have something that's essentially the first, but written in English rather than Math. You gotta convert it into a diagram.

### 1. Let's make it a bit more formal

Look at each part of the given statement that is **bold** (I added in some parenthesis to make the sequence explicit, much like in math—you can do this on your paper as rough work). You can substitute these with a letter from the table above.

> (**thickness is in tolerance** `AND` (**roller speed <> 10 metres/second** `OR` **temperature >= 50 °C**)) `OR` (**roller speed = 10 metres/second** `AND` **temperature >= 50 °C**)

* If the **thickness is in tolerance**, that corresponds to *D=1*.
* If the **roller speed <> 10 metres/second**, that corresponds to *S=0*.

...and so on.

We end up with: (*D=1* `AND` (*S=0* `OR` *T=0*)) `OR` (*S=1* `AND` *T=0*)

Now we make a choice. If something is a 1, we just write its letter (so we just write *D* instead of *D=1*). If it's not a 1 (if it is a 0), we use `NOT` 1 (so we write `NOT` *S*, instead of *S=0*)

Now we end up with: (*D* `AND` ((`NOT` *S*) `OR` (`NOT` *T*))) `OR` (*S* `AND` (`NOT` *T*))

### 2. Figure out which gates you need
Just count:
* 2 `AND` gates
* 2 `OR` gates
* 2 `NOT` gates (the statement above has three, but two of them produce the same output `NOT` *T*, so we can "recycle" this).

### 3. Figure out which values you need.
Looking above, apart from the gates themselves, we have the following:
* *D*
* *T*
* `NOT` *S*
* `NOT` *T*

So we can use *D* as it is provided. We must create a `NOT` *T* and a `NOT` *S*. So start by drawing these out in the space provided. Use the two `NOT` gates from the last step.

### 4. Actually arrange and draw

Now it just comes down to arranging everything and actually drawing it. I cannot really explain this, although I guess you now have enough information to reverse-engineer the mark-scheme. Practice plays a big role here, so if you want, use a textbook (or the internet) to get a hang of this with simpler circuits involving only 2-3 gates at a time. You can also watch people doing this on YouTube, and I think examples are the best way forward for this topic.

## 006-28-10-2021
### Procedures: parameters by reference or by value?

Look at this question.

> The code below uses a procedure.
> 
> ```
> DECLARE name: STRING
> name ← "Sam"
> CALL addMessage(name)
> OUTPUT name
> 
> PROCEDURE addMessage(BYVAL inText: STRING)
>     inText ← "Hello " + inText
> ENDPROCEDURE
> ```
> 
> Explain why this program outputs `Sam` rather than `Hello Sam`.

This is actually a surprisingly subtle concept. So it will take us some time to dissect this. Let's just see two basic ways this procedure can be defined.

### 1: The argument is passed by value, as in the original code

```
DECLARE name: STRING
name ← "Sam"
CALL addMessage(name)
OUTPUT name

PROCEDURE addMessage(BYVAL inText: STRING)
    inText ← "Hello " + inText
ENDPROCEDURE
```


OUTPUT:
```    
Sam
```

Let's break the code down to see what's going on:

1. Define a variable called `name`, and store the value `"Sam"` to it.
2. Go into the procedure `addMessage()`.
3. Create a variable called `inText`, and copy the value of `name` to it. (now whatever you do to `inText` won't affect `name`)
4. Concatenate the literal string `"Hello "` and the value stored in `inText`. Store this new value to `inText`.
5. Exit the procedure.
6. Read the value from `name` and print it out.

We never changed the value of `name`. There is no reason for it to hold anything but the literal `"Sam"` it started with. So that's what it prints.

### 2: The argument is passed by reference, as it should have been

```
DECLARE name: STRING
name ← "Sam"
CALL addMessage(name)
OUTPUT name

PROCEDURE addMessage(BYREF inText: STRING)
    inText ← "Hello " + inText
ENDPROCEDURE
```

OUTPUT:

    Hello Sam

Let's break the code down to see what's going on:

1. Define a variable called `name`, and store the value `"Sam"` to it.
2. Go into the procedure `addMessage()`.
3. Concatenate the literal string `"Hello "` and the value stored in `name`. Store this new value to `name`.
4. Exit the procedure.
5. Read the value from `name` and print it out.

This time, there was no `inText` in the picture. The procedure directly used the variable `name`, and stored the updated value `"Hello Sam"` to it. So when the print statement accesses `name`, it gets the updated value.

### 3: Okay what's this stuff?
In the first case, the computer would pass a **value** to the procedure. Think of it like copying and pasting—whatever you do to the copy won't affect the original.

In the second case, the computer would pass a **reference** to the procedure. Think of it like a link to a website—if someone updates the website, and then you access the link, you get the updated website. In other words, changes to whatever the reference leads to affect the original, and hence any other links.

<br>

Obviously it is a little bit more complicated if you actually break it down into assembly code, but I think this is good enough for you wrap your head around for now. If you're in the mood for getting confused but probably learning more, look up these terms: heap, call stack, pointers.


<br> <br> <br>

[Visit this website's repo](https://github.com/eccentricOrange/CAIE-Computer-Science){: .btn .btn-outline }
