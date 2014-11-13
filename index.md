---

layout: default

style: |
    #Cover h2 {
        margin:65px 0 0;
        color:#FFF;
        text-align:center;
        font-size:70px;
        }
    #Picture h2 {
        color:#FFF;
        }

    .slide>div {
      padding-top: 48px;
    }
    .slide h2 {
      font-size: 48px;
    }

    .slide pre code {
      line-height: 1.5em;
    }

    .picture h2 {
      display: none;
    }

    .godfather {
      background-color: #000;
      color: #FFF;
    }
    .godfather div {
      text-align: center;
      background-image: url(pictures/godfather.png);
      background-size: 75%;
      background-position: 50% 50%;
      background-repeat: no-repeat;
      text-transform: uppercase;
      -webkit-text-stroke-width: 2px;
      -webkit-text-stroke-color: black;
      font-family: Impact;
      font-size: 40px;
    }
    .godfather::after {
      content: '';
    }
    .godfather h2 {
      display: none;
    }
    .godfather .top {
      position: absolute;
      top: 25px;
      width: 800px;
    }
    .godfather .bottom {
      position: absolute;
      bottom: 0;
      width: 800px;
      font-size: 45px;
    }

    .with-link div {
      font-size: 120px;
    }
    .with-link h2 {
      display: none;
    }

---

# JavaScript CodeStyle. Automatically!
{: .cover #Cover }

![](pictures/cover.jpg)

## Codestyle is important
{: .godfather }

You develop but you don't code with respect
{: .top}

You don't even follow the codestyle
{: .bottom }

## JSCS

* <code>
    npm install jscs
  </code>
* Friednly to other tools
* Supported by editors
* Presets
* Tunable

## .jscsrc

    {
        "preset": "airbnb",

        "validateIndentation": 2,
        "requireMultipleVarDecl": true,

        "excludeFiles": [
          "node_modules/**"
        ]
    }

## One by one

    {
        ...

        "excludeFiles": [
          "node_modules/**",
          <mark>"src/**",</mark>
          <mark>"src/parser.js",</mark>
          <mark>"src/server.js"</mark>
        ]
    }

## Pushy
{: .picture }

![](pictures/pushy.jpg)

## Division of responsibility

<table><tr>
<td markdown="1">

### our repository
*must be clean*

* No build to unclean code
* Travis + Github

</td><td markdown="1">

### your repository
*may be clean*

* Editor
* Pre-comit hooks

</td>
</tr></table>

## Check. Then check again

## Some tips

## In of memory

    gulp.task('jscs', function() {
      return gulp.src([
        '**/*.js'
      ])
      <mark class="important">.pipe(gulpIgnore.exclude([</mark>
        <mark class="important">'node_modules/**',</mark>
        <mark class="important">'demo-output/**'</mark>
      <mark class="important">]))</mark>
      .pipe(jscs());
    });

## Never stop watching

    gulp.task('jscs', function() {
      return gulp.src([
        '**/*.js'
      ])
      ...
      <mark class="important">.pipe(plumber())</mark>
      .pipe(jscs());
    });

## Why?
{: .with-link}

[bit.ly/why-jscs](http://bit.ly/why-jscs)

## JSHint ❤ JSCS
{: .jshint }

<blockquote class="twitter-tweet" lang="ru"><p>And with that, JSCS now has all the style enforcement rules that are
being dropped in <a href="https://twitter.com/JSHint">@JSHint</a> 3.0: <a
href="https://t.co/W98EMSiTN5">https://t.co/W98EMSiTN5</a> cc <a
href="https://twitter.com/valueof">@valueof</a></p>&mdash; Mike Sherov (@mikesherov) <a
href="https://twitter.com/mikesherov/status/419596672520318976">4 января 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

## JSLint

<code>
gulp.task('jslint', [ 'jshint', 'jscs' ]);
</code>


## Slide with timer
{: data-timing="00:05" }

It will change right in five seconds

<footer>Presenter note for the first slide</footer>


## Heading

In your slides text you can use [links](http://google.com/) and various inline elements for _emotional_ and **strong** emphasis or just for <i>italic</i> or <b>bold</b> decoration. `<code>` is used for inline code samples.

<footer>Presenter note for the second slide</footer>


## Two rows.<br> Mighty heading

You can use two lines header but it would reduce space on a slide. The “Ribbon” theme is designed for seven lines of code after one-line header by default.

This paragraph could be used as a footnote
{:.note}


## Various lists

- Simple lists are marked with bullets.
- Ordered lists begin with a number.
- You can even nest lists one inside another.
    1. Or mix their types.
    2. But do not go too far.
    3. Otherwise audience will be bored.
- Look, seven rows exactly!


## Serious citation

<figure>
    <blockquote>
        <p>You can wrap one or more paragraphs into citation, which will make text italic and add a nice quote on the left. Giving the citation source would make it even more serious.</p>
    </blockquote>
    <figcaption>Vadim Makeev</figcaption>
</figure>


## When you have a lot of code

    <html lang="en">
    <mark><head></mark> <mark class="comment"><!--Comment--></mark>
        <title>Shower</title>
        <meta charset="<mark class="important">UTF-8</mark>">
        <link rel="stylesheet" href="s/screen.css">
        <script src="j/jquery.js"></script>
    <mark></head></mark>


## Code in separate blocks

    <mark><html</mark> lang="en">

Now you can add a note for each block
{:.note}

    <mark><meta</mark> charset="<mark>UTF-8</mark>">

And explain what is interesting about it
{:.note}


## You can shout<br> this way
{:.shout}


## And place any picture
{:.cover #Picture}

![](pictures/picture.jpg)


## Inner navigation

1. Lets you change objects one by one
2. {:.next} For example, show list items
3. {:.next} Or switch pictures
4. {:.next} And much more
5. {:.next} But it will work only once


## JavaScript Code Style. Automatically

Varya Stepanova, SC5 Online

- [pepelsbey.net](http://pepelsbey.net)
- [twitter.com/pepelsbey](http://twitter.com/pepelsbey)
- [pepelsbey@gmail.com](mailto:pepelsbey@gmail.com)
