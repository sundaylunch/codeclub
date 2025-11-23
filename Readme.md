# Creating an HTML/Javascript Game

## Step 1

First we're going to create a circle on an HTML canvas.

Click on the jsfiddle link:
[jsfiddle example](https://jsfiddle.net/d950m142/)

The html panel contains
```
<canvas id="canvas" width="200" height="200"></canvas>
```

When the html script is loaded, it runs the javascript
The javascript function draws a circle with a radius of 50, and at a position in the middle of the canvas.

```
function drawCircle() {
  var canvas = document.getElementById('canvas');
  var ctx = canvas.getContext('2d');

  // Circle parameters
  var centerX = canvas.width / 2;
  var centerY = canvas.height / 2;
  var radius = 50;

  ctx.beginPath();
  ctx.arc(centerX, centerY, radius, 0, 2 * Math.PI, false);
  ctx.lineWidth = 3;
  ctx.strokeStyle = '#FF0000'; // Red color for the border
  ctx.stroke();

  ctx.fillStyle = 'blue'; // Blue color for the fill
  ctx.fill();
}
```

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

