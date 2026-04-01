---
layout: default
---

# Week 03

[← Back to Home](../index.md)

## Class Communications

### Live Data

At the start of the lesson, there're three example of live data:
 - Dangling String (1995)
 - Tele-Present Wind (2024)
 - Listening Post (2002–2005)

![ ](<../assets/week-03/Screenshot 2026-04-01 at 10.23.45 PM.png>)

![ ](<../assets/week-03/Screenshot 2026-04-01 at 10.24.07 PM.png>)

![ ](<../assets/week-03/Screenshot 2026-04-01 at 10.24.28 PM.png>)

**Dangling String** translated live internet traffic data into the physical spinning of a dangling string,it turns the digital bandwidth into ambient mechanical motion.

**Tele-Present Wind** make live wind data from the perseverance rover on Mars directly to mechanical devices on Earth, it causing dried grass stalks to sway in real-time Martian weather.

**Listening Post** pulls live text data from thousands of simultaneous online chat rooms, projecting them across hundreds of small screens and reading them aloud with a voice synthesizer.

The three example give me a brief idea about what is live data, and how can I presents the live data. I see a fascinating push to pull data out of the abstract digital world and ground it in our physical reality. These examples shows that data can be a living, breathing thing. By translating live information into movement, sound, and physical form.

##

### Asking the Internet Questions

_How would you use the Internet to find out the weather, the definition of a word, or the schedule for your bus home?_

This is always process by App and software from mobile phone and it required internet connection.

### The Command Line

The command line (or terminal) is a text-based interface for communicating with your computer.

Instead of clicking on icons and buttons, you type instructions.

Some things can do with the command line:
 - Navigate files and folders
 - Create and edit plain text files
 - Send emails
 - Run programs
 - **Ask the internet for data**

##

### Navigating Files & Folders

![ ](<../assets/week-03/Screenshot 2026-04-02 at 12.32.53 AM.png>)

![ ](<../assets/week-03/Screenshot 2026-04-02 at 12.36.17 AM.png>)

##

### Creating a File

![ ](<../assets/week-03/Screenshot 2026-04-02 at 12.37.11 AM.png>)

[Screen Roacording for this experiement](https://youtu.be/zpD65meMbOA)

![ ](<../assets/week-03/Screenshot 2026-04-02 at 12.40.06 AM.png>)

##

### Demo 1: ASCII Animations

![ ](<../assets/week-03/Screenshot 2026-04-02 at 12.47.48 AM.png>)

[Screen Roacording for this experiement](https://youtu.be/Gtfxx3xwggs)

##

### Demo 2: Weather

![ ](<../assets/week-03/Screenshot 2026-04-02 at 12.51.09 AM.png>)

[Screen Roacording for this experiement](https://youtu.be/zRek5wLfmZk)

##

### Demo 3: Filtering Live Data

![ ](<../assets/week-03/Screenshot 2026-04-02 at 1.12.33 AM.png>)

[Screen Roacording for this experiement](https://youtu.be/giS21bq3QTc)

##

### Demo 4: Raw Data (JSON)

![ ](<../assets/week-03/Screenshot 2026-04-02 at 1.17.21 AM.png>)

![ ](<../assets/week-03/Screenshot 2026-04-02 at 1.16.50 AM.png>)

##

### Explore with curl

Using your terminal and the GitHub repos for wttr.in and the Free Dictionary API, try to figure out how to:

 - Get the weather for a location using its GPS coordinates

![ ](<../assets/week-03/Screenshot 2026-04-02 at 1.24.34 AM.png>)

 - Get the weather in a different language

![ ](<../assets/week-03/Screenshot 2026-04-02 at 1.25.24 AM.png>)

 - Get the current moon phase

![ ](<../assets/week-03/Screenshot 2026-04-02 at 1.27.31 AM.png>)

 - Look up the synonyms and antonyms of a word

![ ](<../assets/week-03/Screenshot 2026-04-02 at 1.32.40 AM.png>)
Didn't get it.

##

### Application Programming Interface (API)

_**What is an API?**_

An API is a structured way for programs to communicate and exchange data.

When you used curl with wttr.in, you were already using an API: you sent a request to a URL and got data back.

Instead of reading the response in a terminal, the code can read it and do something with it.

##

### Using an API in p5.js

In p5.js, loadJSON() fetches data from a URL, just like curl but inside your sketch.

 - The URL is stored in a variable so it can be reused
 - loadJSON() runs in preload() so the data is ready before the sketch starts
 - The JSON response is stored in the weather object
 - Individual data points are accessed using dot notation, e.g. weather.current.temperature_2m
 - These values are stored in variables (temp, wind, humidity) and used to control visual properties

```
let weather;
let url = "https://api.open-meteo.com/v1/forecast?latitude=-36.85&longitude=174.76&current=temperature_2m,wind_speed_10m,relative_humidity_2m";

function preload() {
  weather = loadJSON(url);
}

function setup() {
  createCanvas(400, 400);
  print(weather.current.temperature_2m);
  print(weather.current.wind_speed_10m);
  print(weather.current.relative_humidity_2m);
}

function draw() {
  let temp = weather.current.temperature_2m;
  let wind = weather.current.wind_speed_10m;
  let humidity = weather.current.relative_humidity_2m;
  
  background(humidity, 100, 200);
  fill('white');
  circle(200, 200, 23.5 * 10);
  fill('red');
  rect(0, 350, wind * 20, 50);
}
```

![ ](<../assets/week-03/Screenshot 2026-04-02 at 1.44.57 AM.png>)

This is what I get paste the code into p5.js

##

### Drawing with Weather

