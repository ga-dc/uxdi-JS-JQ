# Learning Objectives
- Describe the role Javascript plays alongside HTML and CSS.
- Use a JS REPL to test JS code.
- Explain what variables are and why they are used in programming.
- Describe what `strings` and `numbers` are as types of data.
- Get user input using `prompt()`.
- Explain what a function is at a high level and how to pass arguments into it.
- Explain what jQuery is and what problems it solves
- Load jQuery into HTML
- Use jQuery to:
  - Select elements in jQuery.
  - Change text in HTML using jQuery.
  - Change css properties of selected elements.
  - Add an event listener.

## Framing
In the previous classes we went over HTML and CSS. Content and styling. Is that enough? How can we start to think about how things are happening with interactive web pages. Let's take a look at this browser [game](http://jshawl.com/fsm/) ....

## Think-Pair-Share: Identify Javascript features in Super Mario
* 3 minutes: Go look at it. Play with it. Think about what's allowing these behaviors to exist.
* 3 minutes: Discuss and compare findings in pairs.
* Think about what functionality the site has after it has loaded.
* Why would you say a particular feature is "run" by Javascript instead of, say, CSS?

### Findings
- Interactivity
  - Press a key, something happens.
    - Arrow Keys: move Mario.
    - Space: Jump.
  - Javascript defines what happens on a page depending on how you interact with it.
- No Refreshes / User Experience
  - When I move mario, he is able to increment his score without refreshing the page.
  - When I comment on a post, Facebook is able to process my new comment and render it on the page without refreshing the entire page.
  - Gives the page a much smoother user experience compared to a static page that doesn't have this sort of functionality.
- Communication with a server
  - Javascript is somehow telling a server that (a) a user has done something, (b) save that interaction and (c) display the results of that interaction to all other users.

This is not an exhaustive list of Javascript properties, but if you continue to hone your JS skills you'll learn more and more about the different things JS can do.

So, to sum up the main three components of front-end web development up in one word each...
  - HTML: Structure
  - CSS: Styling
  - Javascript: Behavior

# JS: The Client-Side Programming Language of the Web

- Brief history: Created in 10 days by [Brendan Eich](https://twitter.com/BrendanEich).
- *Not* related to Java in any way but its name.
  - "Java" is to "Javascript" as "ham" is to "hamster"

## ST-wg: What's a programming language?

<details>
  <summary>What can it do that a markup language like HTML can't?</summary>
- It let's us do things! It lets us act on information, manipulate it, display it, pretty much whatever we want.
- Javascript enables us to do all that in a browser.
  - Using the tools you learned in the pre-work (e.g., data types, loops, functions).
</details>

## Why is it the dominant programming language of the web?
- Barriers to entry for learning Javascript are very low.
  - No additional software required to run it. Just a text editor and a browser.
    - You can even run it directly in the browser via its Javascript console.
      - Ex. Hide images on the GA website.
      - You'll learn more about the browser Javascript console when you start adding Javascript to the websites you make in this class.
- On top of that, it's supported by all web browsers.
- Javascript has evolved since its creation.
  - One of the biggest additions to JS was AJAX, which allows use to reload parts of a page without refreshing the entire thing (just like on Facebook). Big implications for User Experience.
- A lot of frameworks and libraries -- like jQuery, Angular, and React have emerged that enable us to do so much more, and do it quickly with Javascript.

> Before we start in JS, I want to mention that during the 12 week Web Developmment Immersive, JavaScript is a primary focus for over half the course. That said, this class is 90 minutes long and we're going to jam as much of it in as possible! We'll skip over some of the more in-depth content and get right to the cool parts!

## LES DO EET

[Download this zip file](https://github.com/ga-dc/uxdi-JS-JQ/archive/master.zip)


Let's open up that folder in atom now. We can do this by opening atom then clicking on `File` then `Open`

> This HTML contains just a bit of content that we'll be leveraging later in this class.

In the `script.js` file:

```js
console.log("hello world")
var sentence = "this is a string!"
var number = 5 + 5
```

We might not know what this code is doing at the moment. But for now, let's open the `index.html` file in chrome! If you don't have chrome you'll have to use safari which will have slightly different developer tools.

Next, let's open the developer tools by hitting CMD + OPT + j. You should see the words `hello world`

- The "Console" is a REPL
  - “Read-Eval-Print Loop”.
  - Programming environment that lets us run Javascript code one line at a time.
  - What does it do?
    1. (R)eads our code.
    2. (E)valuates it.
    3. (P)rints it to the console.
    4. Then it (L)oops back to the beginning, ready to (R)ead the next line of code we feed it.

> `⌘ + ⌥ + i` enters you in the the chrome dev tools(if you're using chrome...) Here you can do a bunch of stuff like inspect elements and look at the html. More importantly for this class though, is it allows you to access the console which interacts with the JS you loaded to your page.

The console is a wonderful sandbox where we can test out and play with JS code and see immediate results! If we look back at the code we wrote before:

```js
console.log("hello world")
var sentence = "this is a string!"
var number = 5 + 5
```

There are some things happening. Let's break it down.

First:

```js
console.log("hello world")
```

This function `console.log()` allows us to show some text in our REPL.

Next:

```js
var sentence = "this is a string!"
var number = 5 + 5
```

In these two lines of code we're using variables and storing some values in them. Variables are basically buckets in programming with which we can store data.

The first line, `var sentence = "this is a string!"` is storing a string in the variable `sentence`. If we type in sentence into our REPL, we'll see that string pop out! A string is just a sequence of characters generally delimited by quotation marks.

The next line, `var number = 5 + 5`, is storing the evaluation of `5 + 5`(or 10) into the variable `number`. The thing that's being stored is known as the number data type.

> Numbers and strings have different methods and get treated a bit differently in javascript. IE. there are things you can do with strings that you can't do with numbers and vice versa.

## You do - Try some math operations in the JS console.
Test this code:
```js
5 + 4 * (3 - 1)
```

What does this say about how JS does math operations? (ST - WG)

## User Input (Prompt)
There are many ways to get user input in JS. The easiest way(but probably least common) is to use the `prompt()` function.

Try this out:

```js
var age = prompt("How old are you?")
```

Then type an age into the dialog box. Let's see what happens when we type in `age` and hit enter afterward!

## jQuery

> One thing to note, we'll be using the REPL for alot of this stuff, but know that anything we run in the REPL can be written in our script file and will execute on load of the page!

Great, now that we know the basics, let's do some much cooler things! In order to do these things, let's use the [jQuery](https://jquery.com/) library. Put this code above the existing script tag in your HTML, that part of your HTML should look something like this:

```html
<script src="https://code.jquery.com/jquery-2.2.2.min.js"></script>
<script src="script.js"></script>
<!-- order here is important -->
```

> This loads the jQuery library before our script files. Note: All the things we're about to do with jQuery can be done in just plain 'ol JS, but jQuery makes it a bit easier. jQuery's motto is "write less, do more"

The idea of jQuery is very simple. Select something and then do something to it. There are many parallels with CSS and jQuery.

## Selecting elements
In jQuery, we select elements using `$()`. Inside of the parentheses, we use strings. The string that we use is the same as how we select things in CSS, identical.

Say we want to select an h1, the way we do this is:

```js
$("h1")
```

simple, right? There is a gotcha though. If we have more then one element it will select all of them that match that criteria similarly to CSS.

The way we fix that in CSS is to add classes or ids. In the same way, we can leverage classes and ids in jQuery.

```js
$("p.description")
```

The above code will select a `<p>` tag that has a class of `description`.

## A quick note about functions!
In javascript, there's these things called functions. We can call them on things, call them on their own. Some take arguments, others don't. There are lots and lots of rules about functions and honestly we could probably talk about functions for an entire month and still not be able to cover everything. The TLDR version of functions for this class, is that we can call them on things and sometimes we need to give them information. Like this function we're about to be introduced to!

## Changing Text(using `.html()` function)

Well, I guess that's cool, but how do we do stuff to it? Check this out:

```js
$("h1").html("WHOA! You can do that!?!??!")
```

You sure can.

> This particular function requires 1 argument. The text that you want to be changed to, as a string

## You do - Change the OTHER header

Leveraging what we just learned, Use JS/JQ to change the text of the `h2` in our html

## Changing CSS

I guess that kind of cool, but is there moar?! You betcha. Turns out, we can even change the CSS using JS/JQ.

```js
$("h1").css("color", "lemonchiffon")
```

AWWESSOMME!!

> This function takes 2 arguments. The first argument is the property you'd like to change. The second is the value you'd like it to be. Both strings!

## You do - Change the css of a different element.

Select the `<p>` tag in the HTML and add or change a css property to it.

## Events
This parts a bit tricky but bear with it, it's really cool! Event listeners are a way for us to add behaviors to a web application that makes it interactive. Let's see the basic syntax of one:

```js
$("button").on("click", function(){
  console.log("this button got clicked!")
})
```

> We selected an element, in this case a `button`. Then we write this word `.on`(a function). Then some parentheses. The first thing we put in is the thing we want the `button` to listen for. In this case, a `click`. Then in the function block after we want to describe what we want to happen.

You'll notice that when I click the button, we see those words pop into our REPL.

(ST-WG) Are we limited to the types of code we can write in this block of code? IE. can i do other jQuery things in this block of code?

YES

```js
$("button").on("click", function(){
  $("body").css("background", "blue")
})
```

Cool. This is great, but we barely scratched the surface of the true power of JS and jQuery. I hope you liked this taste!

If you're hungry for more check out these resources:

- [MDN JS Basics Tutorial](https://developer.mozilla.org/en-US/Learn/Getting_started_with_the_web/JavaScript_basics)
- [Tuts Point jQuery Tutorial](http://www.tutorialspoint.com/jquery/)
- [jQuery Documentation](https://api.jquery.com/)
