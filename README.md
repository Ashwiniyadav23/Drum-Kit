## Drum Kit Website Documentation

This documentation explains the structure and functionality of the Drum Kit website built using HTML, CSS, and JavaScript. 

### 1. HTML (`drum.html`)

* **DOCTYPE declaration:** Specifies the document type as HTML5.
* **`<html>` tag:** Root element of the HTML document.
* **`<head>` tag:** Contains metadata about the HTML document.
    * **`<meta charset="UTF-8">`:** Sets the character encoding to UTF-8 for proper display of characters.
    * **`<meta name="viewport" content="width=device-width, initial-scale=1.0">`:** Configures the viewport for responsive design across different devices.
    * **`<title>Drum Kit</title>`:** Defines the title of the HTML document, which appears in the browser tab.
    * **`<link rel="stylesheet" href="drum.css">`:** Links the external CSS file `drum.css` for styling the webpage.
    * **`<link rel="preconnect" href="https://fonts.googleapis.com">` & `<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>`:** Preconnects to Google Fonts servers for faster loading.
    * **`<link href="https://fonts.googleapis.com/css2?family=Permanent+Marker&display=swap" rel="stylesheet">`:** Imports the "Permanent Marker" font from Google Fonts.
    * **`<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">`:** Includes Font Awesome for icons.
* **`<body>` tag:** Contains the content of the HTML document.
    * **`<h1 class="heading">Drum Kit</h1>`:** Main heading of the webpage.
    * **`<div class="keys">`:** Container for all drum keys.
        * **Multiple `<div>` elements with `class="key"`:** Each represents a single drum key, including:
            * **`<kbd>`:** Displays the key that triggers the sound.
            * **`<span class="sound">`:** Holds the name of the sound.
            * **`data-key` attribute:** Specifies the keycode corresponding to the key press.
    * **Multiple `<audio>` elements:** Each represents an audio file for a specific drum sound.
        * **`data-key` attribute:** Same as the `data-key` of the corresponding drum key.
        * **`src` attribute:** Links the audio file.
    * **`<script src="drum.js"></script>`:** Includes the external JavaScript file `drum.js` for functionality.

### 2. CSS (`drum.css`)

* **General Styling:**
    * `body` selector: Sets background color, font, and padding for the entire page.
    * `.heading` selector: Styles the heading with font size, color, and text-align.
* **Drum Key Styling:**
    * `.keys` selector: Sets display, flexbox properties, and padding for the drum key container.
    * `.key` selector: Styles the individual drum keys with size, border-radius, background color, box-shadow, transition, and cursor.
    * `.key:hover` selector: Adds a hover effect to the drum keys, changing the background color.
    * `.key:active` selector: Styles the active state of the key with a darker background color and box-shadow.
    * `.sound` selector: Styles the sound label within each key with font size, color, and text-transform.
    * `.key kbd` selector: Styles the key label within each key with font size, color, and text-transform.

### 3. JavaScript (`drum.js`)

* **Event Listeners:**
    * `addEventListener('keydown', playSound)`: Listens for key presses on the keyboard and calls the `playSound` function.
    * `querySelectorAll('.key').forEach(key => key.addEventListener('click', playSound))`: Adds a click event listener to each drum key, triggering the `playSound` function.
* **playSound Function:**
    * Retrieves the `data-key` attribute from the pressed key or clicked key.
    * Selects the corresponding audio element using the `data-key` value.
    * Plays the selected audio element using the `play()` method.
    * Adds a class `pressed` to the clicked key for visual feedback.
    * Removes the `pressed` class after a short delay using `setTimeout`.

### 4. Functionality

The webpage allows users to trigger drum sounds by either pressing the keys on their keyboard or clicking on the virtual drum keys. 

* Pressing a key triggers the corresponding audio file based on the `data-key` attribute of the key.
* Clicking a drum key triggers the same audio file based on its `data-key` attribute.
* Visual feedback is provided by adding the class `pressed` to the clicked key, which changes its appearance.

### 5. Dependencies

* **Google Fonts:** "Permanent Marker" font.
* **Font Awesome:** For icons.

### Conclusion

This Drum Kit webpage provides a simple and interactive way for users to experiment with different drum sounds. The HTML structure defines the layout, CSS styles the appearance, and JavaScript handles user interactions and sound playback. 
