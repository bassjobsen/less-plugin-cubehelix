Cubehelix plugin for Less
=========================

[Dave Green's `cubehelix' colour scheme](https://www.mrao.cam.ac.uk/~dag/CUBEHELIX/) is intended to be perceived as increasing in intensity. This goes from black to white, deviating away from a pure greyscale (i.e. the diagonal from black to white in a colour cube) using a tapered helix in the colour cube, while ensuring a continuous increase in perceived intensity. The deviation from the diagonal takes into account that red, green and blue are not perceived equally in terms of intensity. This colour scheme prints as a monotonically increasing greyscale on black and white postscript devices.

<a href="http://bost.ocks.org/mike/">Mike Bostock</a> has implemented <i>and extended</i> cubehelix in JavaScript as a
<a href="https://github.com/d3/d3-plugins/tree/master/cubehelix">plugin</a> for the <a href="https://github.com/mbostock/d3">D3.js</a> visualisation library (see
<a href="http://bl.ocks.org/mbostock/11415064">examples</a>), the plugin uses Bostock's JavaScript implementation to extend Less with a cubehelix function.

The cubehelix(y,a,b,t) function returns a color between the two colors a and b, using a gamma correction value of 1. The two colors are typically specified in HSL color space, for starting hue angle 0 < y <= 1 and ending hue angle 0 < t <= 1.


## lessc usage

```
npm install -g less-plugin-cubehelix
```

and then on the command line,

```
lessc file.less --cubehelix
```

Then the following Less code:

```css
p{color: cubehelix(1,red,blue,1);}
p{color: cubehelix(1,red,blue,0.5);}
p{color: cubehelix(1, hsl(300,50%,0%), hsl(-240,50%,100%), 0.3);}
```

outputs:

```css
p {
  color: #766cfd;
}
p {
  color: #21ba40;
}
p {
  color: #4c4c4c;
}

```


## Programmatic usage

```
var LessPluginCubehelix = require('less-plugin-cubehelix'),
    CubehelixPlugin = new LessPluginCubehelix();
less.render(lessString, { plugins: [CubehelixPlugin] })
  .then(
```

## Browser usage

Download [index.js](https://github.com/bassjobsen/less-plugin-cubehelix/blob/master/index.js) and use it as follows:

```html
<script src="index.js"></script>
<script>
less = { 
    plugins: [cubehelix]
};
</script>  
<script src="//cdnjs.cloudflare.com/ajax/libs/less.js/2.1.0/less.min.js"></script>
```


