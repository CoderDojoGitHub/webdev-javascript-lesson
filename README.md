JavaScript Lesson
=================
### CodePen link: http://codepen.io/jensechu/pen/imHpc

## What is JavaScript?
JavaScript is a programming language that your browser speaks. It is how you can add life into your websites by making the elements you put on the page interact with the user, reading your page. We might use it to pop-up an alert box, do some math, or even change the text on your page without editting your HTML! 

## Using the Inspector and console.log();
Unlike HTML and CSS where you can see what changes you make in your Codepen.IO websites, Javascript requires you to use the web inspector's console to see what is going on. The console is a way to see exactly what your JavaScript code is doing, since sometimes you can't tell if your code works or not just by looking at it like in HTML or CSS.

* To get started open your JavaScript window in CodePen.io.
* Type in ``console.log("CoderDojo is awesome!")``

## Talking to JavaScript
Let's give your website some personality.
First, we should teach your website your name! In your JavaScript section type in and see what this does:
* ``prompt("What is your name, page visitor?")``

You should see an alert box pop up that has a place to type in your name. Go ahead and tell your webpage what your name is! In your Inspector's Console you should see your name in quotation marks.

## What is a function?
A function is a command that will run some code every time you type it in. For example, every time you type in ``prompt("What is your name?")``, a new alert box will pop up on your website. 

Functions are important because usually you want to control when certain code will run on your site. Let's try adding some code that will allow us to click on a link to run our ``prompt()`` function, instead of running our ``prompt()`` function when our page loads.

Functions are just a set of instructions to return the value that you want. It is similar to how baking a cake might have a recipe to follow to always bake the same cake.

* First we need to add a button to our HTML. ``<button href="#" class="round-button" onClick="prompt('What is your name?')">Click Me!</button>``
* Now lets make the button look more like a button by adding some css.


```
.round-button {
  background: #33CCFF;
  color: #FFFFFF; 
  border-radius: 50px;
  padding: 20px;
  font-size: 20px;
}
```

* Now try clicking your button. You can see that using ``onclick="prompt('What is your name?')"`` on the HTML element allowed you to have some control of when the ``prompt()`` is used.

## Using Variables
Variables in JavaScript let you save data with associated names. Let's try teaching our script what our name is, since right now if we just run ``prompt("What is your name?")`` our script has no way to recall our name again. 

* In your JavaScript Inspector try: ``console.log(name);``
* Then add ``var name = prompt('What is your name?')``
* Now try ``console.log(name)`` in your Inspector again. 
* Why do you think these are different?
* Be sure to delete these three lines of code when you are finished typing them so we can write our own function to get your name.

You can name your variable almost anything, but it can't start with a number. Variable names also can't be any of JavaScript's [Reserved Words](http://msdn.microsoft.com/en-us/library/0779sbks.aspx)

## Writing your own function.
We will write two functions to get your name and birth year so we can use those values later in our code.

### Your Name
Here we will write a function to return your name.
* We need a button in our HTML to run our code: ``<button class="round-button" onClick="getMyName()">What is your name?</button>``
* And now in our JavaScript:

```
// Log my name
var getMyName = function() {
  var name = prompt("What is your name?");
  console.log("Hello " + name + "!");
  return name
}
```


### Birth Year
Now that we have taught your script to remember your name using variables, let's write our own function that will tell you the year you were born by subtracting your age from the current year. 
* In your JavaScript type:

```
// Return my Birth Year
var myBirthYear = function( age ) {
  var currentYear = 2013;
  var birthYear = currentYear - age
  console.log(birthYear);
  return birthYear
}
```

## Adding Data to Your Page
All of our JavaScript data is just stored in our JavaScript code right now. But what if we wanted to display our data on the website? Let's create a welcome message for our users.
* First lets add an HTML element for our welcome message. ``<div id="welcome-container"></div>``
* We also need a button to run our function: ``<button class="round-button" onclick="setWelcomeMessage()>Set Welcome Message!</button>"``
* Add some CSS

```
#welcome-container {
  font-size: 25px;
  padding: 20px;
  background: #33ffcc;
  margin: 20px;
  border: 10px dotted white;  
}
```
* Paste this code into your JavaScript section:

```
// Set a welcome message with my data
var setWelcomeMessage = function() {
  var name = getMyName();
  var birthYear = myBirthYear(prompt('What is your age?'));
  
  var welcomeContainer = document.getElementById('welcome-container');
  var welcomeMessage = "Your name is " + name + ", and your was born in " + birthYear + "!";
  
  welcomeContainer.innerHTML = welcomeMessage;
}
```
Notice how we are using the two functions we already wrote in our JavaScript to get our ``name`` and ``birthYear`` values.

Keep in mind that browsers are forgetful! They cannot remember everything you do unless we tell our code to make the browser remember. When we refresh our page, the name and birthYear you stored will be gone.

