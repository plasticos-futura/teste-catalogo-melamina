<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Catalogue Flipbook</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="flipbook-header">
            <h1>Product Catalogue</h1>
        </div>

        <div class="flipbook-wrapper">
            <div id="flipbook"></div>
        </div>

        <div class="controls">
            <button id="prevBtn" class="nav-btn">← Previous</button>
            <span id="pageInfo" class="page-info">Page 1 of 1</span>
            <button id="nextBtn" class="nav-btn">Next →</button>
        </div>

        <div class="additional-controls">
            <button id="fullscreenBtn" class="control-btn">Fullscreen</button>
            <button id="downloadBtn" class="control-btn">Download PDF</button>
            <input type="range" id="zoomSlider" class="zoom-slider" min="50" max="200" value="100">
            <span id="zoomLevel">100%</span>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.min.js"></script>
    <script src="flipbook.js"></script>
</body>
</html>
