---
layout: page
title: About
permalink: /about/
---

## Intro
<p>Hi, My name is Sonika Dhenuva Konda, I go by Soni. I am in 10th grade and 15 years old.</p>
<p>I joined a few clubs at school like Robotics & Debate. I also own my own small buisness of selling jewlry</p>

## My Favorites
<p>My favorite food is icecream, i also love any type of chocolate</p>
<p>I also have several favorite movie such as all Ironman, Deadpool, Spiderman, Sherlock Homes, Transformers, Rush Hour, Jurrasic World, etc</p>
<img src="{{site.baseurl}}/images/jurassic.png">
<img src="{{site.baseurl}}/images/deadpool.png">
<img src="{{site.baseurl}}/images/spiderman.png">


## My Family
<p>Fun Fact! I was actually born in india. I moved here when I was 9 months old. My dad and mom are both from India, and I have a younger sister who is 9.</p>
<p> A lot of my family, including grandparents, aunts, uncles, and cousin are in Indian and love to go and visit then once in a few years!</p>
<img src="{{site.baseurl}}/images/india.png">
<img src="{{site.baseurl}}/images/food.png">




# Github Pages Playground
<p>This is the Github Playground w/ Games</p>
{%include nav/github_pages.html %}







# FrontEnd Devolpment
<html> 

<div style="border:dashed" > 
<h2 color="white"> HELLO </h2>
<p> Soni Dhenuva </p>
<br>
<button id="myButton">Dont Click this.</button>
<p id="responseMessage"></p>
<script src="script.js"></script>
</div>


<script>
const button = document.getElementById('myButton');
const message = document.getElementById('responseMessage');
// Add an event listener to the button for the click event
button.addEventListener('click', function() {
    // Change the message when the button is clicked
    message.textContent = "I will find you";
});
</script>






<div style="border:dashed"> 
<a href="https://sallysbakingaddiction.com/strawberry-cake/"> Strawberry Cake Recipie</a>
<br>

<a href="https://sallysbakingaddiction.com/the-great-pumpkin-pie-recipe/">Pumpkin Pie Recipie</a>
<br>
<p> Which recipe do like better? </p>
</div>

</html>

# Javascript Calculator

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="style.css">
    <style>
        .calculator-container {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 5px;
            max-width: 220px;
            margin: 20px auto;
        }
        .calculator-output {
            grid-column: span 4;
            border-radius: 10px;
            padding: 0.5em;
            font-size: 24px;
            border: 2px solid black;
            background-color: #f1f1f1;
            display: flex;
            align-items: center;
            justify-content: flex-end; /* Right-justify result */
            box-sizing: border-box;
        }
        .calculator-button {
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #e0e0e0;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 20px;
            cursor: pointer;
            height: 50px;
            width: 100%;
            box-sizing: border-box;
        }
        .calculator-button:hover {
            background-color: #d0d0d0;
        }
        .calculator-clear {
            grid-column: span 4;
            background-color: #ff6666;
            color: white;
        }
        .calculator-equals {
            grid-column: span 4;
            background-color: #66cc66;
            color: white;
        }
    </style>
</head>
<body>

<!-- Add a container for the animation -->
<div id="animation">
    <div class="calculator-container">
        <!-- Result -->
        <div class="calculator-output" id="output">0</div>
        <!-- Row 1 -->
        <div class="calculator-button calculator-number">1</div>
        <div class="calculator-button calculator-number">2</div>
        <div class="calculator-button calculator-number">3</div>
        <div class="calculator-button calculator-operation">+</div>
        <!-- Row 2 -->
        <div class="calculator-button calculator-number">4</div>
        <div class="calculator-button calculator-number">5</div>
        <div class="calculator-button calculator-number">6</div>
        <div class="calculator-button calculator-operation">-</div>
        <!-- Row 3 -->
        <div class="calculator-button calculator-number">7</div>
        <div class="calculator-button calculator-number">8</div>
        <div class="calculator-button calculator-number">9</div>
        <div class="calculator-button calculator-operation">/</div> <!-- Division button -->
        <!-- Row 4 -->
        <div class="calculator-button calculator-clear">A/C</div>
        <div class="calculator-button calculator-number">0</div>
        <div class="calculator-button calculator-number">.</div>
        <div class="calculator-button calculator-equals">=</div>
    </div>
</div>

<!-- JavaScript (JS) implementation of the calculator -->
<script>
    var firstNumber = null;
    var operator = null;
    var nextReady = true;
    const output = document.getElementById("output");
    const numbers = document.querySelectorAll(".calculator-number");
    const operations = document.querySelectorAll(".calculator-operation");
    const clear = document.querySelector(".calculator-clear");
    const equals = document.querySelector(".calculator-equals");

    // Number buttons listener
    numbers.forEach(button => {
        button.addEventListener("click", function() {
            number(button.textContent);
        });
    });

    // Number action
    function number(value) {
        if (value != ".") {
            if (nextReady) {
                output.textContent = value;
                nextReady = value != "0";
            } else {
                output.textContent += value;
            }
        } else {
            if (!output.textContent.includes(".")) {
                output.textContent += value;
            }
        }
        nextReady = false;
    }

    // Operation buttons listener
    operations.forEach(button => {
        button.addEventListener("click", function() {
            operation(button.textContent);
        });
    });

    // Operator action
    function operation(choice) {
        if (firstNumber === null) {
            firstNumber = parseFloat(output.textContent);
            operator = choice;
            nextReady = true;
        } else {
            firstNumber = calculate(firstNumber, parseFloat(output.textContent));
            operator = choice;
            output.textContent = firstNumber.toString();
            nextReady = true;
        }
    }

    // Calculator
    function calculate(first, second) {
        let result = 0;
        switch (operator) {
            case "+":
                result = first + second;
                break;
            case "-":
                result = first - second;
                break;
            case "*":
                result = first * second;
                break;
            case "/":
                result = second === 0 ? "Error" : first / second;
                break;
            default:
                break;
        }
        return result;
    }

    // Equals button listener
    equals.addEventListener("click", function() {
        equal();
    });

    // Equal action
    function equal() {
        firstNumber = calculate(firstNumber, parseFloat(output.textContent));
        output.textContent = firstNumber.toString();
        nextReady = true;
    }

    // Clear button listener
    clear.addEventListener("click", function() {
        clearCalc();
    });

    // A/C action
    function clearCalc() {
        firstNumber = null;
        output.textContent = "0";
        nextReady = true;
    }
</script>

<!-- Vanta animations just for fun, load JS onto the page -->
<script src="https://cdn.jsdelivr.net/npm/three@0.119.0/build/three.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/vanta@0.5.3/dist/vanta.halo.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/vanta@0.5.3/dist/vanta.birds.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/vanta@0.5.3/dist/vanta.net.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/vanta@0.5.3/dist/vanta.rings.min.js"></script>

<script>
    var vantaInstances = {
        halo: VANTA.HALO,
        birds: VANTA.BIRDS,
        net: VANTA.NET,
        rings: VANTA.RINGS
    };

    var vantaInstance = vantaInstances[Object.keys(vantaInstances)[Math.floor(Math.random() * Object.keys(vantaInstances).length)]];

    vantaInstance({
        el: "#animation",
        mouseControls: true,
        touchControls: true,
        gyroControls: false
    });
</script>
</body>
</html>

## Cookie Clicker Game

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cookie Clicker</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f5f5f5;
        }
        .game-container {
            text-align: center;
        }
        .cookie-button {
            cursor: pointer;
            background: none;
            border: none;
            outline: none;
            font-size: 150px; /* Size of the cookie */
            transition: transform 0.2s;
        }
        .cookie-button:hover {
            transform: scale(1.1);
        }
        .cookie-count {
            font-size: 36px;
            margin: 20px 0;
            color: white; /* Set text color to white */
        }
        .buy-button {
            padding: 10px 20px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            background-color: #4caf50;
            color: white; /* Set button text color to white */
            cursor: pointer;
            margin: 10px;
            transition: background-color 0.3s;
        }
        .buy-button:hover {
            background-color: #45a049;
        }
        .info {
            font-size: 16px;
            margin: 10px 0;
            color: white; /* Set info text color to white */
        }
    </style>
</head>
<body>

<div class="game-container">
    <button id="cookieButton" class="cookie-button" onclick="cookieClick()">
        🍪
    </button>
    <div id="cookieCount" class="cookie-count">Cookies: 0</div>
    <div id="productionRate" class="info">Cookies per second: 0</div>
    <div id="upgradeSection">
        <div class="info">
            <button id="buyGrandma" class="buy-button">Buy Grandma: +1 Cookie/Second (Cost: 50 Cookies)</button>
            <button id="buyFactory" class="buy-button">Buy Factory: +5 Cookies/Second (Cost: 500 Cookies)</button>
        </div>
    </div>
</div>

<script>
    let cookieCount = 0;
    let cookiesPerClick = 1;
    let cookiesPerSecond = 0;
    let grandmaCost = 50;
    let factoryCost = 500;

    function updateDisplay() {
        document.getElementById('cookieCount').textContent = `Cookies: ${cookieCount}`;
        document.getElementById('productionRate').textContent = `Cookies per second: ${cookiesPerSecond}`;
        document.getElementById('buyGrandma').textContent = `Buy Grandma: +1 Cookie/Second (Cost: ${grandmaCost} Cookies)👵`;
        document.getElementById('buyFactory').textContent = `Buy Factory: +5 Cookies/Second (Cost: ${factoryCost} Cookies) 🏭`;
    }

    function cookieClick() {
        cookieCount += cookiesPerClick;
        updateDisplay();
    }

    document.getElementById('buyGrandma').onclick = function() {
        if (cookieCount >= grandmaCost) {
            cookieCount -= grandmaCost;
            cookiesPerSecond += 1;
            grandmaCost = Math.floor(grandmaCost * 1.15); // Increase cost for next Grandma
            updateDisplay();
        } else {
            alert('Not enough cookies for Grandma!');
        }
    };

    document.getElementById('buyFactory').onclick = function() {
        if (cookieCount >= factoryCost) {
            cookieCount -= factoryCost;
            cookiesPerSecond += 5;
            factoryCost = Math.floor(factoryCost * 1.15); // Increase cost for next Factory
            updateDisplay();
        } else {
            alert('Not enough cookies for Factory!');
        }
    };

    function increaseCookies() {
        cookieCount += cookiesPerSecond;
        updateDisplay();
    }

    setInterval(increaseCookies, 1000);
</script>

</body>
</html>

<br>
<br>

## JavaScript API
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>iTunes Search</title>
    <style>
      body {
        background-color: #333; /* Dark background for contrast */
      }
      table {
        width: 100%; /* Full width table */
        border-collapse: collapse; /* Collapses borders */
      }
      th, td {
        border: 1px solid #fff; /* White border for visibility */
        padding: 8px; /* Padding for cells */
        text-align: left; /* Left-align text */
        color: white; /* Change text color to white */
      }
      th {
        background-color: #444; /* Darker background for header */
      }
      tr:nth-child(even) {
        background-color: #555; /* Lighten even rows for contrast */
      }
      tr:hover {
        background-color: #666; /* Highlight on hover */
      }
    </style>
</head>
<body>

<div>
  <input type="text" id="filterInput" placeholder="Enter iTunes filter">
  <button onclick="fetchData()">Search</button>
</div>

<!-- HTML table fragment for page -->
<table>
  <thead>
    <tr>
      <th>Artist</th>
      <th>Track</th>
      <th>Images</th>
      <th>Preview</th>
    </tr>
  </thead>
  <tbody id="result">
    <!-- generated rows -->
  </tbody>
</table>

<!-- Script is laid out in a sequence (no function) and will execute when the page is loaded -->
<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("result");

  // function to fetch data based on user input
  function fetchData() {
    // clear previous results
    resultContainer.innerHTML = "";

    // get user input
    const filterInput = document.getElementById("filterInput");
    const filter = filterInput.value;

    // prepare fetch options
    const url = "https://itunes.apple.com/search?term=" + encodeURIComponent(filter);
    const headers = {
      method: 'GET',
      mode: 'cors',
      cache: 'default',
      credentials: 'omit',
      headers: {
        'Content-Type': 'application/json'
      },
    };

    // fetch the API
    fetch(url, headers)
      .then(response => {
        // check for response errors
        if (response.status !== 200) {
          const errorMsg = 'Database response error: ' + response.status;
          console.log(errorMsg);
          const tr = document.createElement("tr");
          const td = document.createElement("td");
          td.innerHTML = errorMsg;
          tr.appendChild(td);
          resultContainer.appendChild(tr);
          return;
        }
        // valid response will have JSON data
        response.json().then(data => {
          console.log(data);

          // Music data
          for (const row of data.results) {
            console.log(row);

            // tr for each row
            const tr = document.createElement("tr");
            // td for each column
            const artist = document.createElement("td");
            const track = document.createElement("td");
            const image = document.createElement("td");
            const preview = document.createElement("td");

            // data is specific to the API
            artist.innerHTML = row.artistName;
            track.innerHTML = row.trackName; 
            // create preview image
            const img = document.createElement("img");
            img.src = row.artworkUrl100;
            image.appendChild(img);
            // create preview player
            const audio = document.createElement("audio");
            audio.controls = true;
            const source = document.createElement("source");
            source.src = row.previewUrl;
            source.type = "audio/mp4";
            audio.appendChild(source);
            preview.appendChild(audio);

            // this builds td's into tr
            tr.appendChild(artist);
            tr.appendChild(track);
            tr.appendChild(image);
            tr.appendChild(preview);

            // add HTML to container
            resultContainer.appendChild(tr);
          }
        })
      })
      .catch(err => {
        console.error(err);
        const tr = document.createElement("tr");
        const td = document.createElement("td");
        td.innerHTML = err;
        tr.appendChild(td);
        resultContainer.appendChild(tr);
      });
  }
</script>

</body>
</html>