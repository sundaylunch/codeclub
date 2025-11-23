# Creating an HTML/Javascript Game

## Step 1

First we're going to create a circle on an HTML canvas.

Click on the jsfiddle link:
[jsfiddle example](https://jsfiddle.net/d950m142/2/)

The html panel contains
```
<canvas id="canvas" width="200" height="200"></canvas>
```

When the html script is loaded, it runs the javascript
The javascript function draws a circle with a radius of 50, and at a position in the middle of the canvas.

## Step 2

Add a border using CSS - this is used to style HTML pages.

Paste the below code into the CSS panel in JSFiddle

```
canvas {
    border: 3px solid #ccc;
}
```

Press run, you should see a border drawn around your canvas!

#ccc represents the colour of the border - it should be a light gray

Change this to your own colour (if you click on the small gray circle next to #ccc you will get a colour picker).

Don't forget to press run to see the change!

![fiddle screenshot](fiddle_screenshot.png "Example image")

## Step 3

Change the width and height of the <b>canvas</b> - have a look at the html code, and see if you can make the canvas three times as big!

## Step 4

Make the circle appear in a random place in the canvas.
The javascript function <b>Math.random()</b> will gives a random value between 0 and 1.

The centre of the circle is set using <b>X</b> and <b>Y</b>

Change the part of the code that sets X and Y like this:

``
  var X = canvas.width * Math.random();
  var Y = canvas.height * Math.random();
``

Try pressing Run several times and see what happens!


## Step 5

Instead of having to re-run the page, let's draw a new circle when you click on the canvas!

We need to add an event listener which listens to the "click" event, and calls a function.

Instead of drawing a circle when the page is loaded, we'll add these two lines to the top of the Javascript:

```
var canvas = document.getElementById('canvas');
canvas.addEventListener("click",drawCircle);
```

To make it a bit easier to see, you can change the panel layout of JsFiddle to <b>tabs</b> like this:

![fiddle screenshot](fiddle_2.png "Example image")

When you click on the canvas you should see lots of circles appearing!

## Step 6

Now we're going to set up some variables to keep track of where the circles are, and what size they are.

This will come in handy later!

Add these three lines to the top of the javascript:

```
var circles = [];
var COUNT = 0;
var MAX = 4;
```

This is going to create some <b>variables</b>:

* <b>circles</b> - an <b>array<b> to track every circle on the page (an array is like a list in scratch)
* <b>COUNT</b> - the number of circles on the page
* <b>MAX</b> - the maximum number of circles allowed on the page

Now in the draw function code we need to add some code to <b>count</b> the number of circles we drew.
And stop you drawing too many circles!

Change the drawCircles() function to put and <b>IF</b> block around it - in javascript the curly braces go around a block of code

if (COUNT < MAX) { }

is the same as:

![scratch if block](scratch_if_statement.png "Scratch if example image")


```
function drawCircle() {

  if (COUNT < MAX) {
  COUNT++;
  var canvas = document.getElementById('canvas');
  var ctx = canvas.getContext('2d');

  // Circle parameters
  var X = canvas.width * Math.random();
  var Y = canvas.height * Math.random();
  var radius = 50;
  circles.push({X,Y,radius});

  ctx.beginPath();
  ctx.arc(X, Y, radius, 0, 2 * Math.PI, false);
  ctx.lineWidth = 3;
  ctx.strokeStyle = '#FF0000'; // Red color for the border
  ctx.stroke();

  ctx.fillStyle = 'blue'; // Blue color for the fill
  ctx.fill();
  }
}
```