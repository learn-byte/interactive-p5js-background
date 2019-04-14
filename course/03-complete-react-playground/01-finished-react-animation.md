# Finishing touches

#### The only thing left to do for this sketch is getting it centered on the page. Then we can, ship it 🚢!

One way to get some quick styles for our page is to throw the styles right in with our code. We can do this by declaring a stlyes object like so:

```
const styles = {
    "text-align": "center",
    "position":"absolute",
    "top":"50%",
    "left":"50%",
    "transform":"translate(-50%, -50%)"
}
```

Once we add our `styles` to the top level `div` in `App.js`, the content should all be centered horizontally and vertically.

#### Here is what our app looks like! It's ready for adding new animiation experiments.

![final-app](https://raw.githubusercontent.com/learn-byte/interactive-p5js-background/master/assets/images/final-app.png)


#### Here is our final code for `App.js`:

```
import React, { Component } from 'react';
import P5Wrapper from 'react-p5-wrapper';

const sketch = (p) => {
  p.setup = function () {
    p.createCanvas(750, 500);
  };
  p.draw = function () {
    const randomGrayFill = Math.floor(Math.random() * 256)
    p.fill(randomGrayFill)
    p.ellipse(p.mouseX, p.mouseY, 25, 25);
  };
}

class App extends Component {
  render() {
    const styles = {
      "text-align": "center",
      "position":"absolute",
      "top":"50%",
      "left":"50%",
      "transform":"translate(-50%, -50%)"
    }
    return (
      <div style={styles}>
        <h1>🔥 p5.js animation playground 🔥</h1>
        <P5Wrapper sketch={sketch} />
      </div>
    );
  }
}

export default App;
```