# Putting our sketch into our React app

#### In just a few quick minutes we put together a hello world sketch and a hello world react app, how can we combine the two of them together?

We will need a react node module to help us get the sketch into our app.

From the `my-animation-app` directory install [react-p5-wrapper](https://www.npmjs.com/package/react-p5-wrapper):

`npm install --save react-p5-wrapper`

#### Setup your sketch

Next, in a text editor of your choice (we like [VS Code](https://code.visualstudio.com/)) open our react code for `my-animation-app`.  

Open `App.js` in the `src` directory.

We will remove most of the boilerplate code in this file. In it's place we will use our new P5Wrapper component to create a sketch right in our React app.

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
    return (
      <div>
        <h1>🔥 p5.js animation playground 🔥</h1>
        <P5Wrapper sketch={sketch} />
      </div>
    );
  }
}

export default App;
```

We can pretty much use the exact same code we made in our hello world. Except, now we need to use the props passed into our sketch as `p` wherever we are invoking a method from p5.js.  

So, making an ellipse goes from `ellipse()` to `p.ellipse()`.

Once we save the code, the page should reload and our animation should be working!