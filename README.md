# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨
HTML: (index.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Animation with Preferences</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <button id="animateBtn">Click Me!</button>
  <div id="animatedBox" class="box"></div>
  <script src="script.js"></script>
</body>
</html>
 CSS: (styles.css)
body {
  font-family: Arial, sans-serif;
  text-align: center;
  padding: 50px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #3498db;
}

.box {
  width: 100px;
  height: 100px;
  margin: 20px auto;
  background-color: #2ecc71;
  transition: transform 0.5s ease, background-color 0.5s ease;
}

.box.animate {
  transform: rotate(360deg);
  background-color: #e74c3c;
}
 JavaScript: (script.js)
// script.js

// Function to apply saved preferences
function applyPreferences() {
  const savedColor = localStorage.getItem('boxColor');
  if (savedColor) {
    document.getElementById('animatedBox').style.backgroundColor = savedColor;
  }
}

// Function to handle button click
function handleButtonClick() {
  const box = document.getElementById('animatedBox');
  box.classList.add('animate');

  // Save the new color preference
  localStorage.setItem('boxColor', '#e74c3c');

  // Reset animation after it ends
  setTimeout(() => {
    box.classList.remove('animate');
  }, 500);
}

// Apply preferences on page load
applyPreferences();

// Add event listener to the button
document.getElementById('animateBtn').addEventListener('click', handleButtonClick);

