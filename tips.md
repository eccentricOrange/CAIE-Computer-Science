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

Depending on your experience with programming, the line `x = x + 1` may be either daunting or completely obvious. How can something be equal to one added to itself? Solving mathematically, we get something meaningless:

$$\begin{align}
x &= x + 1 \newline
x - x &= x + 1 - x \newline
0 &= 1
\end{align}$$

![Spongebob based meme](https://i.imgur.com/XydhvcK.png)

Nevertheless, if you're ever confused with something like this, there is always one thing which can sort it out: **convert it to something like assembly language**. Obviously, actual assembly-level programming can get rather complex, but simple sentences that elaborate a line of high-level code can help clarify its purpose/meaning.

From the example above, the line `x = x + 1` would break down like this:

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
6. Optionally add sugar
7. Optionally add milk
8. Stir

...it might be bit confusing. But if I just told you to make tea, you'd get what I'm trying to say.

## 005-19-10-2021
### Logic gate diagrams

I'll take question **5 (a)**, of the paper with paper code `0478/13/M/J/16`, as an example for explaining how to translate a logic statement into a logic diagram. You may find it helpful to try and draw your own circuit along my explanation (or look at the solution from the marking scheme if you're really stuck).

<br>

Recognize that there are two ways to represent logic operations (at the level of IGCSE). The first is a statement, and the second is a diagram. You have something that's essentially the first, but written in English rather than Math. You gotta convert it into a diagram.

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


## 007-15-11-2021
### Common mistakes in Python

James Murphy over at the YouTube channel [mCoding](https://www.youtube.com/c/mCodingWithJamesMurphy/) just did an excellent video about common mistakes people make when learning Python. I highly recommend you watch it.

**WARNING:** While many of the things he points out are genuine problems, and in real projects you should try to follow best practices, for an exam please follow your textbooks. If you board has an endorsed, or otherwise recommended book, please follow the syntax and practices recommended by those books.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qUeud6DvOWI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


## 008-19-03-2022
### YouTube series about networking

If you're beginning to learn about networking and internet, I would highly recommend [Internet 101](https://youtube.com/playlist?list=PLSQl0a2vh4HD8wtmKZh0nKOsOvP1KYaNO) by Khan Academy. It covers a lot of the basics and should give you a good intuitive understanding for grasping your textbooks.

<iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLSQl0a2vh4HD8wtmKZh0nKOsOvP1KYaNO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


## 009-10-06-2022
### Understanding Object-oriented Programming
I gave the following explanation in a [Reddit comment](https://www.reddit.com/r/CodingHelp/comments/ri7fte/oop_python/howj7xn/?context=3).

> I'm going to give you a number of analogies here. Don't dwell too much on any given example, we'll link it to coding later.
> 
> BTW, I'm generalizing this answer so that it's about OOP irrespective of languages. But I'll show you a snippet of Python code at the end.
> 
> #### \#1 Think of a specific chair
> * **There are going to be some things about the chair that you can think about.** It will have a height of 1 metre, a mass of 2 kg, a black colour, maybe a memorable dent in the hind leg etc.
> * **What does it do?** Nothing really.
> * **What can happen to it?** It can be moved around, it can be cleaned, it can be broken (yikes!) etc.
> 
> #### \#2 Think of a specific bus
> I'm imagining my school bus.
> * It is yellow, it had seats for 60 people, I'm assuming there's 20 litres of fuel in it right now. It had my school's crest painted on the right side.
> * **What does it do?** It can move or brake. It can accelerate or decelerate.
> * **What can happen to it?** It can be boarded or deboarded, it can be driven, it can be cleaned etc.
> 
> #### \#3 Think of a specific human
> I'm imagining a fictions friend.
> * She's 1.7 m tall, has a mass of 62 kg, is kind, is honest, is extremely lazy.
> * **What can she do?** She can study, eat, breathe, run, think etc
> * **What can happen to her?** Can be transported somewhere, can be requested something, can fall asleep etc.
> 
> #### \#4 Now think of all possible chairs
> You cannot state the colour of all chairs. It doesn't make sense. You don't know the dents of all chairs. But you do know that all of them will have some colour.
> 
> You can clean most of them and you can sit on most of them. But you don't know if you move all of them around—some may be fixed to the floor.
> 
> #### \#5 Think of all possible buses
> Again, you cannot know the colour of all of the buses, but you can be certain that each bus will have a colour. You cannot know the level of fuel of all the buses, but all of them will have some level (even if it's 0).
> 
> Most of them can move or brake, but some might be broken. Most of them can be cleaned.
> 
> #### \#6 Think of all possible humans
> I don't know every human's height and mass, but every human has a measurable height and mass. I don't know how lazy most humans are, however.
> 
> Almost every human can breathe and eat. Almost every human can fall asleep. Not all of them can run (e.g. paralyzed people), but a lot can.
> 
> #### Takeaways
> Do you see what we're doing here?
> 
> We're assigning some **properties** (such as the level of fuel in a bus) to each _thing_. When we talk about a specific thing, the property has a **value** (such as 20 litres of fuel in the bus). Some things may not share these properties; e.g., if a bus is still under construction, its fuel tank may not have been installed yet so its level of fuel is undefined.
> 
> We're also talking about what they can do or what can be done to them. These are **methods** (basically functions or procedures, depending on what they do). Most humans will have the method that they can breathe. Again, many humans will have the running method, but some will not.
> 
> When we're talking about things in general (a generalized chair, for example), we're talking about the **class** of chairs. The chair I'm currently sitting in is an **instance** of that class. Your chair is a different instance of the chair class. If the class chair has a method that they can be cleaned, that both our chairs will "get" that method. This process of creating a specific **object** (such as your chair or my chair) from the class (such as the generalized idea of a chair) is called **instantiating**.
> 
> But that's repetitive. When discussing the chairs, I had to state that it can be cleaned even though I already mentioned that when I discussed buses. So lets make a **parent class** of non-living things. We'll say that the class of buses and the class of chairs are both **children** of the class of non-living things. Now if I say that non-living things can be cleaned, all buses and chairs will inherit that.
> 
> If there is a specific historical instance of chair sitting in a sterile museum, we don't want people touching it. So for that instance, we can specify that it cannot be cleaned.
> 
> #### What's this got to do with programming?
> See for yourself! (Python 3)
> 
> ```py
> class non_living_things:
>     def get_cleaned(self):
>         print("Being cleaned.")
> 
> class bus(non_living_things):
>     colour = ""
>     fuel_level = 0.0
>     number_of_seats = 0
> 
>     def be_driven(self):
>         print("Driving.")
> 
>     def get_boarded(self):
>         print("Getting boarded.")
> 
>     def accelerate(self):
>         print("Accelerating.")
> 
> class chair(non_living_things):
>     colour = ""
>     mass = 0.0
>     height = 0.0
> 
>     def get_moved_around(self):
>         print("Moving around.")
> 
> my_chair = chair()
> my_chair.colour = "black"
> my_chair.mass = 2
> my_chair.height = 1
> my_chair.get_cleaned()
> my_chair.get_moved_around()
> 
> your_chair = chair()
> your_chair.colour = "red"
> your_chair.mass = 2.7
> your_chair.height = 1.5
> your_chair.get_cleaned()
> your_chair.get_moved_around()
> 
> my_bus = bus()
> my_bus.colour = "yellow"
> my_bus.fuel_level = 20
> my_bus.number_of_seats = 60
> my_bus.get_cleaned()
> my_bus.be_driven()
> ```
> 
> Don't stress on stuff like the word `self` for now, it's a rather nuanced concept.

## 010-05-11-2022
### Check out Harvard University's CS50!

For the uninitiated, [CS50 Introduction to Computer Science](http://cs50.harvard.edu/) is probably Harvard University's most popular class. It provides a good foundation for learning about computer science and programming, with a lecturer that makes the topics fairly approachable.

The link above takes you to their main edX page where you can browse all of their classes and learn more about its certifications. IGCSE and AS & A Level students may find it easier to approach the following links, which will take you directly to specific CS50 courses:

* [Main CS course](https://cs50.harvard.edu/x) (covers introductory computer science but with significant rigour; mostly in the C language)
* [Python-specific course](https://cs50.harvard.edu/python) (covers introductory computer science; completely in the Python language)


<br> <br> <br>

[Visit this website's repo](https://github.com/eccentricOrange/CAIE-Computer-Science){: .btn .btn-outline }
