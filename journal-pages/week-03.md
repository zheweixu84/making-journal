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

![ ](<../assets/week-03/Screenshot 2026-04-02 at 1.48.42 AM.png>)

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

I got the same image drawing out, and I notice there's a console at the bottom of the coding section.

![ ](<../assets/week-03/Screenshot 2026-04-02 at 1.51.10 AM.png>)

##

### Using the Console

![ ](<../assets/week-03/Screenshot 2026-04-02 at 1.53.28 AM.png>)

Now I understand what the shapes are meaning, the higher the tempureture is the larger the circle will be. This can make the user easier see the relations between the different informations.

##

### Live Updates

The weather sketch fetches data once in the preload() function.

Some data moves fast…

The International Space Station orbits Earth at ~28,000 km/h. Its position changes every second.

![alt text](<../assets/week-03/Screenshot 2026-04-02 at 1.57.00 AM.png>)

![alt text](<../assets/week-03/Screenshot 2026-04-02 at 1.57.47 AM.png>)

These two screenshots are only in 10seconds and some of the informations are change.

##

### ISS Tracker

This sketch calls the API every 5 seconds and updates a dot and text on the canvas.

 - setInterval() calls fetchISS() on a timer
 - loadJSON() takes a callback — a function that runs when the data arrives
 - The ISS position is used directly to move the dot
 - We need the if conditional statement to check the data has been received

```
let issData;

let issData;

function fetchISS() {
  let url = "https://api.wheretheiss.at"
    + "/v1/satellites/25544";
  loadJSON(url, function(data) {
    issData = data;
  });
}

function setup() {
  createCanvas(400, 400);
  fetchISS();
  setInterval(fetchISS, 5000);
}

function draw() {
  background(0);
  if (issData) {
    fill('red');
    circle(200 + issData.longitude, 200 - issData.latitude, 20);
    text("Lat: " + issData.latitude, 10, 20);
    text("Lon: " + issData.longitude, 10, 40);
  }
}
```

![ ](<../assets/week-03/Screenshot 2026-04-02 at 2.01.41 AM.png>)

And this information of Lat and Lon is also keep changing.

##

### Simulating Live Data

![ ](<../assets/week-03/Screenshot 2026-04-02 at 2.03.18 AM.png>)

### Weather Visualisation

Open the weather sketch in the p5.js web editor and experiment with how you map the data to visual forms.

Some things to try:

 - Change the location (latitude and longitude)
 - Use the data to control different visual properties: colour, position, size, number of shapes
 - Add more weather variables from the Open-Meteo docs to your API URL
 - Use random() or noise() alongside or instead of the live data
 - Use vibe coding to try something more ambitious

 ```
let weather;
// 1. Changed location to Tokyo (Lat: 35.68, Long: 139.76) 
// 3. Added 'cloud_cover' to the API URL
let url = "https://api.open-meteo.com/v1/forecast?latitude=35.68&longitude=139.76&current=temperature_2m,wind_speed_10m,relative_humidity_2m,cloud_cover";

let noiseOffset = 0;

function preload() {
  weather = loadJSON(url);
}

function setup() {
  createCanvas(400, 400);
  
  // Quick check in the console to see the data
  console.log("Temp:", weather.current.temperature_2m);
  console.log("Wind:", weather.current.wind_speed_10m);
  console.log("Humidity:", weather.current.relative_humidity_2m);
  console.log("Cloud Cover:", weather.current.cloud_cover);
}

function draw() {
  let temp = weather.current.temperature_2m;
  let wind = weather.current.wind_speed_10m;
  let humidity = weather.current.relative_humidity_2m;
  let clouds = weather.current.cloud_cover; // New variable!
  
  // 2. Control visual properties: Background mapped to humidity
  // Map humidity (0-100) to a scale of dark blue to bright blue
  let bgBlue = map(humidity, 0, 100, 50, 255);
  background(10, 30, bgBlue);
  
  // 4. Use noise() alongside live data to make a dynamic "sun"
  // The size is controlled by live temperature, but it vibrates with noise
  let baseSize = map(temp, -10, 40, 50, 200); // Maps temp to a reasonable size
  let sunSize = baseSize + noise(noiseOffset) * 30; 
  noiseOffset += 0.05; // Drives the noise forward
  
  noStroke();
  fill(255, 204, 0);
  circle(width / 2, height / 2, sunSize);
  
  // 2. Control number of shapes using cloud cover data
  // Draws small white circles based on the current cloud percentage
  fill(255, 255, 255, 150); // Semi-transparent white
  let numberOfClouds = floor(map(clouds, 0, 100, 0, 50));
  
  for (let i = 0; i < numberOfClouds; i++) {
    // We use random seeds or set positions so they don't flicker wildly every frame
    randomSeed(i); 
    let cx = random(width);
    let cy = random(0, height / 2);
    let cSize = random(20, 60);
    circle(cx, cy, cSize);
  }
  
  // 2. Control position and size with wind speed
  // A ground bar that gets taller and changes color based on wind
  let windHeight = map(wind, 0, 50, 10, 150);
  let redTone = map(wind, 0, 50, 100, 255);
  fill(redTone, 50, 50);
  rect(0, height - windHeight, width, windHeight);
  
  // Text readout
  fill(255);
  textSize(14);
  text(`Temp: ${temp}°C`, 20, 30);
  text(`Wind: ${wind} km/h`, 20, 50);
  text(`Clouds: ${clouds}%`, 20, 70);
}
 ```

[Screen Roacording for this experiement](https://youtube.com/shorts/-oFfIsCLvn0?feature=share)

