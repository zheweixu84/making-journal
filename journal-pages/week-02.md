---
layout: default
---

# Week 02

[← Back to Home](../index.md)

## Class Communications

### Interactivity in These Project

The projects shown from the last week is been rediscussed.

- The visualisation changes based on what people do
- Data is collected through the interaction, not just displayed
- The experience of engaging with the data is part of the meaning
- Physical materials and space shape how people encounter information 

##

## Experiment 2 - Interativity

### From Physical to Digital

We will use p5.js to do some data drawings and interactive. It is a JavaScript library designed to make coding accessible for artists, designers and beginners.

I can adds buttons, sliders, input fields, dropdown menus to my drawings. By advanced coding techniques, I can even make some particle effects.

##

### Setting up and learn the basics

I create a p5.js account.

And have a learn about the overview of the interface.

![ ](<../assets/week-02/Screenshot 2026-04-01 at 2.35.24 PM.png>)

And the next step is to Setup the function, I learned how to create a canvas. by use the function "createCanvas()" and "setup()". And by using the draw function, the "draw()" function continuously executes the lines of code contained inside its block until the program is stopped.

```
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
}
```
![ ](<../assets/week-02/Screenshot 2026-04-01 at 2.55.11 PM.png>)

##

### Starting Experiment

The p5.js follow the coordinate space which is the x axis and y axis to represents the position while creating images on canvas.

The first function I tried is to create a circle.

Then I learned how to create comment on the code, which will not shown on the canvas, this is a useful tool to remind myself of what a piece of code does.


```
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background('white'); // set background to white
  fill('red'); // fill shapes with red
  strokeWeight(0); // no outline for shapes
  circle(250,250,50); // circle at (250,250) with a size of 50
}
```

![ ](<../assets/week-02/Screenshot 2026-04-01 at 2.54.35 PM.png>)

And the programe is run from top to bottom of the code, and one step at a time.

```
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background('white');
  fill('red');
  strokeWeight(0);
  circle(250,250,50);
  fill('blue');
  circle(100,100,50);
}
```

This code will be looking like:

![ ](<../assets/week-02/Screenshot 2026-04-01 at 3.18.16 PM.png>)

##

### Reference

There's a whole page of reference about the p5.js coding, it explain all the functions and how toi use all these different functions.

![ ](<../assets/week-02/Screenshot 2026-04-01 at 3.06.56 PM.png>)

We go through some fundamental functions such as circle, fill, StrokeWeight, Background. 

##

### Experimentation

![ ](<../assets/week-02/Screenshot 2026-04-01 at 3.20.25 PM.png>)

I follow the instruction and use the rectangle, triangle, line and ellipse tool to make the image on the right.

```
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background('rgb(0,0,0)');
  fill('#FFEB3B');
  strokeWeight(0);
  circle(200,250,100);
  fill('#4CAF50');
  rect(0, 250, 400, 200);
  
  stroke('rgb(0,0,0)');
  strokeWeight(1);
  line(0, 250, 400, 250);
}
```

![ ](<../assets/week-02/Screenshot 2026-04-01 at 3.23.17 PM.png>)

I found that by changing the order of the instruction, the image will change, such as if I type in the code for the green rectangle first then I type the circle. the circle will be on top of the rectangle due to the programme sequence.

I think I didn't perfectly match the image it given, becauser the origin image is not a perfect square and the canvas I create is a perfect square.

##

## Coding funamentals

### Variables

 - Variables are how we store data in our program. 
 - A variable has a name and a value.

We use "**let**" to create one.  
Change the value of size and run the program again.

```
let size = 80;

function setup() {
  createCanvas(400, 400);
}

function draw() {
  background('white');
  fill('red');
  circle(200, 200, size);
}
```
![alt text](<../assets/week-02/Screenshot 2026-04-01 at 4.18.14 PM.png>)

![alt text](<../assets/week-02/Screenshot 2026-04-01 at 4.18.22 PM.png>)

I change the size value from 80 to 200 and the size of the circle is changing.

Because the value named : "size". And it been repalced as "d" which is the diameter of the circle.

##

### Updating Variables

 - The funcrion "draw()" will run 60 times per seconds,

 - Because "draw()" runs over and over, we can change a variable in each frame.

 ```
 let xPos = 0;

function setup() {
  createCanvas(400, 400);
}

function draw() {
  background('white');
  fill('red');
  circle(xPos, 200, 80);
  xPos = xPos + 1;
}
```
[Watch the video](https://youtu.be/_2tKOkOmvTc)



