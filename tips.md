---
nav_order: 7
---

<script async="">
    window.MathJax = {
        tex: {
            inlineMath: [['$', '$'], ['\\(', '\\)']]
        },
        svg: {
            fontCache: 'global'
        },
        jax: ["input/TeX", "output/CommonHTML"]
    };


    (function () {
        var script = document.createElement('script');
        script.src = 'https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js';
        script.async = true;
        document.head.appendChild(script);
    })();
</script>

# Tips and tricks

I often find myself wanting to discuss little tips, tricks, and other ideas, but they don't merit a full article. So I'll keep posting them here. Each tip has a number and the date when I first wrote it in the format `XXX-DD-MM-YYYY` (where `XXX` is the number), so that it can easily be found later.

**Note:** There is no defined release schedule for these tips.

## 001-09-10-2021: Foo, Bar, and Baz
If you decide to look for help online, especially on a forum full of professional programmers (such as Stack Overflow), you might find these three words — among others — thrown around a lot.

They are [metasyntactic variables](https://en.wikipedia.org/wiki/Metasyntactic_variable), arbitrary variables used as placeholders. There is no specific meaning behind them, much like how $x$, $y$, $t$ etc are used to define other expressions in mathematics.

Further reading:
* [Foobar \(Wikipedia\)](https://en.wikipedia.org/wiki/Foobar)
* [Meaning of foo, bar, baz, etc \(Stack Overflow\)](https://stackoverflow.com/questions/34212049/meaning-of-foo-bar-baz-etc)

<br> <br> <br>

[Visit this website's repo](https://github.com/eccentricOrange/CAIE-Computer-Science){: .btn .btn-outline }