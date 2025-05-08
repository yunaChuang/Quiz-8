## Quiz-8
For quiz 8, inspiration of group project
Week 9

# Part 1: Imaging Technique Inspiration
### Concentric pattern
> I want to combine the centrical pattern part into the project. For ripples, it is easier to apply which only include circles with certain x and y position. Concentric patterns can be used with mouse or as a signal. Therefore, the connection with "Wheels of fortune" would support this idea to dedicate to main project. 

-  Ripple (concentric circle)
![This is for alt text.](/assets/ripple.jpg "this is just a ripple image.")

# Part 2:
### Ripple
1. Draw Code
```
function draw() {
  background(255);
  
  // Display and update ripples
  for (let i = ripples.length - 1; i >= 0; i--) {
    ripples[i].display();
    ripples[i].update();
    
    // Remove ripples when they fade out
    if (ripples[i].alpha <= 0) {
      ripples.splice(i, 1);
    }
  }
}
```
> This code use loop to  draw ripples. Keep making the circle smaller until it disappears.
 2. Mouse code
 ```
 function mouseMoved() {
  let rippleSize = random(50, 200);
  let rippleAlpha = random(100, 255);
  let newRipple = new Ripple(mouseX, mouseY, rippleSize, rippleAlpha);
  ripples.push(newRipple);
}
```
> This part is about mouseMoved so the center of the ripple will follow users' mouse. The default size and alpha for penetration are random.
3. Class
```
class Ripple {
  constructor(x, y, size, alpha) {
    this.x = x;
    this.y = y;
    this.size = size;
    this.alpha = alpha;
    this.maxSize = size * 2;
  }
    display() {
    stroke(0, this.alpha);
    ellipse(this.x, this.y, this.size);
  }
    update() {
    this.size += 2;
    this.alpha -= 2;
  }
}
```
> Set a class called ripple. Display the ripple. Enlarge the circles and decrease their alpha to make them looks like ripples.

Code for ripple press [here](https://openprocessing.org/sketch/1979024).