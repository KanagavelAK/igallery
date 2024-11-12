# Ex.07 Design of Interactive Image Gallery
## Date: 12/11/24

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
### HTML:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Photo Gallery</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Interactive Photo Gallery</h1>
    <div class="gallery">
        <div class="photo" data-title="Image 1">
            <img src="image1.jpg" alt="Image 1">
            <div class="caption">Train</div>
        </div>
        <div class="photo" data-title="Image 2">
            <img src="image2.jpg" alt="Image 2">
            <div class="caption">Sparrow</div>
        </div>
        <div class="photo" data-title="Image 3">
            <img src="image3.jpg" alt="Image 3">
            <div class="caption">Dog</div>
        </div>
        <div class="photo" data-title="Image 4">
            <img src="image4.jpg" alt="Image 4">
            <div class="caption">Flower</div>
        </div>
        <div class="photo" data-title="Image 5">
            <img src="image5.jpg" alt="Image 5">
            <div class="caption">Deer</div>
        </div>
        <div class="photo" data-title="Image 6">
            <img src="image6.jpg" alt="Image 6">
            <div class="caption">Mountain</div>
        </div>
        <div class="photo" data-title="Image 7">
            <img src="image7.jpg" alt="Image 7">
            <div class="caption">Snow road</div>
        </div>
        <div class="photo" data-title="Image 8">
            <img src="image8.jpg" alt="Image 8">
            <div class="caption">Architecture</div>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

```
### CSS
```
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    min-height: 100vh;
    background-color: #23ad9d;
}

h1 {
    margin-bottom: 20px;
    font-size: 2em;
    color: #ffffff;
}

.gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 20px;
    width: 90%;
    max-width: 1000px;
}

.photo {
    position: relative;
    width: 100%;
    height: 200px;
    overflow: hidden;
    background-color: #ddd;
    border-radius: 15px;
    transform: perspective(600px);
    transition: transform 0.4s ease;
    cursor: pointer;
}

.photo img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.4s ease;
    border-radius: 15px;
}

.photo:hover {
    transform: rotateY(10deg) scale(1.05);
}

.photo:hover img {
    filter: brightness(0.8);
}

.caption {
    position: absolute;
    bottom: -40px;
    left: 0;
    width: 100%;
    background: rgba(117, 117, 117, 0.7);
    color: white;
    font-size: 1em;
    text-align: center;
    padding: 10px;
    transition: bottom 0.4s ease;
    border-bottom-left-radius: 15px;
    border-bottom-right-radius: 15px;
}

.photo:hover .caption {
    bottom: 0;
}

```
### JAVASCRIPT
```
// Function to handle mouseover event
function handleMouseOver(event) {
    const photo = event.currentTarget;
    const caption = photo.querySelector('.caption');

    // Rotate and scale up the photo
    photo.style.transform = "rotateY(10deg) scale(1.05)";
    photo.querySelector('img').style.filter = "brightness(0.8)";

    // Slide up the caption
    caption.style.bottom = "0";
}

// Function to handle mouseleave event
function handleMouseLeave(event) {
    const photo = event.currentTarget;
    const caption = photo.querySelector('.caption');

    // Reset transform and brightness
    photo.style.transform = "rotateY(0deg) scale(1)";
    photo.querySelector('img').style.filter = "brightness(1)";

    // Hide the caption
    caption.style.bottom = "-40px";
}

// Add event listeners for each photo in the gallery
document.querySelectorAll('.photo').forEach(photo => {
    photo.addEventListener('mouseover', handleMouseOver);
    photo.addEventListener('mouseleave', handleMouseLeave);
});
```
## OUTPUT:
![Screenshot 2024-11-12 222605](https://github.com/user-attachments/assets/4b3d873a-5a20-4330-b78e-b4c1dea4a7a8)

![Screenshot 2024-11-12 223632](https://github.com/user-attachments/assets/4a117e35-a857-405e-a58b-db364cdf434f)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
