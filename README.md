# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


# Tasks
- Create a well-structured HTML5 document.


     # index.html
  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript DOM Manipulation</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            text-align: center;
        }
        .container {
            margin: 30px 0;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        button {
            padding: 10px 15px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            margin: 5px;
        }
        button:hover {
            background-color: #45a049;
        }
        .dynamic-element {
            padding: 15px;
            margin: 10px 0;
            background-color: #f8f8f8;
            border-left: 4px solid #4CAF50;
        }
    </style>
</head>
<body>
    <h1>JavaScript DOM Manipulation</h1>
    
    <div class="container">
        <h2 id="change-text">Original Text Content</h2>
        <button id="text-changer">Change Text</button>
    </div>
    
    <div class="container">
        <p id="style-target">This paragraph will change style when you click the button.</p>
        <button id="style-changer">Change Style</button>
    </div>
    
    <div class="container">
        <div id="element-container">
            <div class="dynamic-element">This is a dynamic element</div>
        </div>
        <button id="toggle-element">Toggle Element</button>
    </div>

    <script src="script.js"></script>
</body>
</html>


# script.js
// Wait for DOM to be fully loaded
document.addEventListener('DOMContentLoaded', function() {
    // 1. Change text content dynamically
    const textChangerBtn = document.getElementById('text-changer');
    const textElement = document.getElementById('change-text');
    
    textChangerBtn.addEventListener('click', function() {
        textElement.textContent = 'Text changed dynamically with JavaScript!';
    });
    
    // 2. Modify CSS styles via JavaScript
    const styleChangerBtn = document.getElementById('style-changer');
    const styleTarget = document.getElementById('style-target');
    
    styleChangerBtn.addEventListener('click', function() {
        styleTarget.style.color = '#FF5733';
        styleTarget.style.fontSize = '20px';
        styleTarget.style.fontWeight = 'bold';
        styleTarget.style.backgroundColor = '#FFFACD';
        styleTarget.style.padding = '10px';
    });
    
    // 3. Add or remove element when button is clicked
    const toggleElementBtn = document.getElementById('toggle-element');
    const elementContainer = document.getElementById('element-container');
    let elementExists = true;
    
    toggleElementBtn.addEventListener('click', function() {
        if (elementExists) {
            elementContainer.innerHTML = '';
            toggleElementBtn.textContent = 'Add Element';
        } else {
            elementContainer.innerHTML = '<div class="dynamic-element">This is a dynamic element</div>';
            toggleElementBtn.textContent = 'Remove Element';
        }
        elementExists = !elementExists;
    });
});












