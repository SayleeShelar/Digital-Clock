# Digital Clock using JavaScript

This project is a simple digital clock implemented using HTML, CSS, and JavaScript. It displays the current time, updating every second. The project was created following a tutorial on the GreatStack YouTube channel.

## Features

- Displays the current time in hours, minutes, and seconds.
- Updates every second to reflect the current time.
- Responsive design with a visually appealing clock interface.

## Preview

![Digital Clock](path/to/your/screenshot.png)

## How to Run the Project

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/SayleeShelar/digital-clock.git
   ```

2. **Navigate to the Project Directory:**
   ```sh
   cd digital-clock
   ```

3. **Open the `index.html` file in your browser:**
   You can open the file directly by double-clicking on it or by using a live server extension in your code editor.

## Code Explanation

### HTML

The HTML file sets up the basic structure of the digital clock. It includes references to the external CSS and JavaScript files.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Digital Clock using JavaScript</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="hero">
        <div class="container">
            <div class="clock">
                <span id="hrs">00</span>
                <span>:</span>
                <span id="min">00</span>
                <span>:</span>
                <span id="sec">00</span>
            </div>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
```

### CSS

The CSS file contains the styling for the digital clock, including layout, colors, and fonts.

```css
*{
    margin: 0;
    padding: 0;
    font-family: 'Poppins', sans-serif;
    box-sizing: border-box;
}

.hero {
    width: 100%;
    min-height: 100vh;
    background: linear-gradient(45deg, #08001f, #30197d);
    color: #fff;
    position: relative;
}
.container {
    width: 800px;
    height: 180px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
.clock {
    width: 100%;
    height: 100%;
    background: rgba(235, 0, 255, 0.11);
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    backdrop-filter: blur(40px);
}
.container::before {
    content: '';
    width: 180px;
    height: 180px;
    background: #f41b75;
    border-radius: 5px;
    position: absolute;
    left: -50px;
    top: -50px;
    z-index: -1;
}
.container::after {
    content: '';
    width: 180px;
    height: 180px;
    background: #419aff;
    border-radius: 50%;
    position: absolute;
    right: -30px;
    bottom: -50px;
    z-index: -1;
}
.clock span {
    font-size: 80px;
    width: 110px;
    display: inline-block;
    text-align: center;
    position: relative;
}
.clock span::after {
    font-size: 16px;
    position: absolute;
    bottom: -5px;
    left: 50%;
    transform: translatex(-50%);
}
#hrs::after {
    content: 'HOURS';
}
#min::after {
    content: 'MINS';
}
#sec::after {
    content: 'SEC';
}
```

### JavaScript

The JavaScript file contains the logic to update the time every second.

```javascript
let hrs = document.getElementById("hrs");
let min = document.getElementById("min");
let sec = document.getElementById("sec");

setInterval(() => {
    let currentTime = new Date();
    hrs.innerHTML = (currentTime.getHours() < 10 ? "0" : "") + currentTime.getHours();
    min.innerHTML = (currentTime.getMinutes() < 10 ? "0" : "") + currentTime.getMinutes();
    sec.innerHTML = (currentTime.getSeconds() < 10 ? "0" : "") + currentTime.getSeconds();
}, 1000);
```

## Acknowledgements

This project was developed following a tutorial from the [GreatStack YouTube channel](https://www.youtube.com/c/GreatStack).

## License

This project does not have a specific license. All rights reserved. If you wish to use this project for any purpose, please contact the author.

---

