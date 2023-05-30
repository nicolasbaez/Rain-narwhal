# Rain-narwhal
Rainy cubes

![buh](https://github.com/nicolasbaez/Rain-narwhal/blob/main/xp005.gif)
```javascript
p = (i, x, y, h) => {
  push();
  n = map(sin(i) / i, 0, 1, 0, h);
  translate(x, y + n, n);
  rotate(n * 0.1);
  box(18);
  pop();
};
setup = (_) => {
  c = 500;
  createCanvas(c, c, WEBGL);
  saveGif("xp005", 10);
};
i = 0;
w = 250;
draw = (_) => {
  rotateY(1);
  background(0);
  for (j = -w; j < w; j += 45) {
    for (k = -w; k < w; k += 45) {
      p(i, j, k, noise(j, k) * c);
    }
  }
  i += 0.2;
};
