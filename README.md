## Quiz-8
For quiz 8, inspiration of group project
Week 9

| Name      | Unikey        |
| --------- |:-------------:|
| Yuan-Yuan | ychu0126      |

# Part 1: Imaging Technique Inspiration
### Concentric pattern
> I plan to combine the concentrical patterns into the project. Ripple effect involves circles with certain x and y position is the main idea. This patterns can be used with mouse, as a signal or just directly add to the artwork. By connecting this technique with "Wheels of fortune" by Pacita Abad, support me to bring this element to our main project. 

-  Ripple (concentric circle)
![ripple 1](/assets/ripple.jpg "this is just a ripple image.")
![ripple 2](/assets/rippling-water-abstract-stockcake.jpg "this is just a ripple image.")
- Artwork from Pacita Abad
![by Pacita Abad](/assets/919.3567.jpg "this is another artwork from Pacita Abad.")

---
# Part 2: Coding Technique Exploration
### Ripple
1. Draw
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
 2. Mouse
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

More code for ripple press [here](https://openprocessing.org/sketch/1979024).