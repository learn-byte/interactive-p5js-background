# Simple p5.js sketch

### How do you write a hello world for a visual programming langauge?  Draw circles!

Every p5.js sketch needs two basic functions to do anything interesting. A `setup()` function and a `draw()` function.  

We start with a `setup()` function that creates our drawing space for us.  We will create our canvas as 800px wide by 500 px tall.

```
function setup() {
  createCanvas(800, 500);
}

function draw() {
  var randomGrayFill = Math.floor(Math.random() * 256)
  fill(randomGrayFill)
  ellipse(mouseX, mouseY, 25, 25);
}
```
Then we create a `draw()` function that will create random shades of gray circles that will follow our mouse.  

The first line of the function assigns a randomGrayFill color, then we fill all shapes with that random color, and finally we draw an ellipse centered around our current mouse coordinates and give it a size of 25px wide. 

#### Hello, visual world!

![gray-circles](https://raw.githubusercontent.com/learn-byte/interactive-p5js-background/master/assets/images/gray-circles.png)

Play with and [edit this sketch here](https://editor.p5js.org/compcuter/sketches/VEURqY2Ju).