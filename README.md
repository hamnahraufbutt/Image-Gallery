# Image-Gallery
 Image Gallery Project  A simple image gallery built using HTML, CSS, and JavaScript. The gallery showcases a collection of images in a responsive layout with hover effects and interactive features.  Features  - Responsive grid layout - Hover effects for image enlargement - Modal view for full-size images
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 20px;
}

.gallery {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
}

.gallery-item {
    width: 30%;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s;
}

.gallery-item img {
    width: 100%;
    display: block;
}

.gallery-item:hover {
    transform: scale(1.05);
}
document.addEventListener('DOMContentLoaded', () => {
    const galleryItems = document.querySelectorAll('.gallery-item img');
    galleryItems.forEach(item => {
        item.addEventListener('click', () => {
            openModal(item.src);
        });
    });

    function openModal(src) {
        const modal = document.createElement('div');
        modal.className = 'modal';
        modal.innerHTML = `
            <div class="modal-content">
                <span class="close-button">&times;</span>
                <img src="${src}" alt="Full Size Image">
            </div>
        `;
        document.body.appendChild(modal);

        const closeButton = modal.querySelector('.close-button');
        closeButton.addEventListener('click', () => {
            document.body.removeChild(modal);
        });
    }
});
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Gallery</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="gallery">
        <div class="gallery-item">
            <img src="image1.jpg" alt="Image 1">
        </div>
        <div class="gallery-item">
            <img src="image2.jpg" alt="Image 2">
        </div>
        <div class="gallery-item">
            <img src="image3.jpg" alt="Image 3">
        </div>
        <div class="gallery-item">
            <img src="image4.jpg" alt="Image 4">
        </div>
        <div class="gallery-item">
            <img src="image5.jpg" alt="Image 5">
        </div>
        <div class="gallery-item">
            <img src="image6.jpg" alt="Image 6">

        <!-- Add more images as needed -->
    </div>
    <script src="script.js"></script>
</body>
</html>


