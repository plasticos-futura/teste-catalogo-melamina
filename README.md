<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Embalagens Melamina - Catálogo</title>
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>📦 Embalagens Melamina</h1>
            <p>Catálogo Completo</p>
        </div>

        <div class="flipbook-container">
            <div id="flipbook" class="flipbook">
                <div class="page page-cover">
                    <div class="cover-content">
                        <h1>Embalagens Melamina</h1>
                        <p>Catálogo Completo</p>
                    </div>
                </div>
            </div>
        </div>

        <div class="controls">
            <button id="prevBtn" class="btn-control">
                <i class="fas fa-chevron-left"></i> Anterior
            </button>
            <span id="pageInfo" class="page-info">Página 1</span>
            <button id="nextBtn" class="btn-control">
                Próxima <i class="fas fa-chevron-right"></i>
            </button>
        </div>

        <div class="extra-controls">
            <button id="fullscreenBtn" class="btn-extra">
                <i class="fas fa-expand"></i> Tela Cheia
            </button>
            <button id="downloadBtn" class="btn-extra">
                <i class="fas fa-download"></i> Baixar PDF
            </button>
            <div class="zoom-control">
                <label>Zoom:</label>
                <input type="range" id="zoomSlider" min="50" max="200" value="100">
                <span id="zoomLevel">100%</span>
            </div>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
    <script src="flipbook.js"></script>
</body>
</html>

{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --primary-color: #667eea;
    --secondary-color: #764ba2;
    --text-color: #333;
    --border-color: #ddd;
    --shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
    min-height: 100vh;
    padding: 20px;
    color: var(--text-color);
}

.container {
    max-width: 1000px;
    margin: 0 auto;
    background: white;
    border-radius: 15px;
    box-shadow: var(--shadow);
    overflow: hidden;
}

/* Header */
.header {
    background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
    color: white;
    padding: 30px;
    text-align: center;
}

.header h1 {
    font-size: 2.5em;
    margin-bottom: 10px;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
}

.header p {
    font-size: 1.1em;
    opacity: 0.95;
}

/* Flipbook Container */
.flipbook-container {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 40px 20px;
    background: linear-gradient(to bottom, #f9f9f9, #f0f0f0);
    min-height: 650px;
}

.flipbook {
    position: relative;
    width: 100%;
    max-width: 900px;
    aspect-ratio: 16 / 12;
    perspective: 1200px;
}

.page {
    position: absolute;
    width: 100%;
    height: 100%;
    background: white;
    box-shadow: var(--shadow);
    border-radius: 5px;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0;
}

.page img, .page canvas {
    width: 100%;
    height: 100%;
    object-fit: contain;
    display: block;
}

/* Page Cover */
.page-cover {
    background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
    color: white;
    text-align: center;
}

.cover-content {
    text-align: center;
    z-index: 10;
}

.cover-content h1 {
    font-size: 3em;
    margin-bottom: 20px;
    text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.3);
}

.cover-content p {
    font-size: 1.5em;
    opacity: 0.9;
}

/* Flipbook Animation */
.flip-animation {
    animation: pageFlip 0.6s ease-in-out;
}

@keyframes pageFlip {
    0% {
        transform: rotateY(0deg);
        opacity: 1;
    }
    100% {
        transform: rotateY(90deg);
        opacity: 0;
    }
}

/* Controls */
.controls {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
    padding: 25px;
    background: #f5f5f5;
    border-top: 2px solid var(--border-color);
    flex-wrap: wrap;
}

.btn-control {
    padding: 12px 25px;
    font-size: 1em;
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: white;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: all 0.3s ease;
    font-weight: 600;
    display: flex;
    align-items: center;
    gap: 8px;
}

.btn-control:hover:not(:disabled) {
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
}

.btn-control:disabled {
    background: #ccc;
    cursor: not-allowed;
    opacity: 0.6;
}

.page-info {
    font-size: 1.2em;
    font-weight: bold;
    color: var(--text-color);
    min-width: 120px;
    text-align: center;
    background: white;
    padding: 8px 15px;
    border-radius: 20px;
    border: 2px solid var(--primary-color);
}

/* Extra Controls */
.extra-controls {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 15px;
    padding: 20px;
    background: white;
    border-top: 1px solid var(--border-color);
    flex-wrap: wrap;
}

.btn-extra {
    padding: 10px 20px;
    font-size: 0.95em;
    background: var(--secondary-color);
    color: white;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    gap: 8px;
    font-weight: 600;
}

.btn-extra:hover {
    background: var(--primary-color);
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(118, 75, 162, 0.4);
}

.zoom-control {
    display: flex;
    align-items: center;
    gap: 10px;
    background: #f9f9f9;
    padding: 8px 15px;
    border-radius: 8px;
}

.zoom-control label {
    font-weight: 600;
    color: var(--text-color);
}

.zoom-control input {
    width: 120px;
    cursor: pointer;
}

#zoomLevel {
    font-weight: bold;
    min-width: 45px;
    color: var(--secondary-color);
}

/* Responsive Design */
@media (max-width: 768px) {
    .header h1 {
        font-size: 1.8em;
    }

    .flipbook-container {
        min-height: 400px;
        padding: 20px 10px;
    }

    .flipbook {
        max-width: 100%;
    }

    .controls {
        gap: 10px;
    }

    .btn-control {
        padding: 10px 15px;
        font-size: 0.9em;
    }

    .page-info {
        min-width: 100px;
        font-size: 1em;
    }

    .extra-controls {
        flex-direction: column;
        gap: 10px;
    }

    .btn-extra {
        width: 100%;
        justify-content: center;
    }

    .zoom-control {
        width: 100%;
        justify-content: center;
    }
}

@media (max-width: 480px) {
    .header h1 {
        font-size: 1.4em;
    }

    .header


// Configure PDF.js
const pdfjsLib = window['pdfjs-dist/build/pdf'];
pdfjsLib.GlobalWorkerOptions.workerSrc = 'https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.worker.min.js';

// State
let pdfDoc = null;
let currentPage = 1;
let totalPages = 0;
let currentZoom = 100;
const pdfUrl = './Embalagens Melamina.pdf';

// DOM Elements
const flipbookDiv = document.getElementById('flipbook');
const prevBtn = document.getElementById('prevBtn');
const nextBtn = document.getElementById('nextBtn');
const pageInfo = document.getElementById('pageInfo');
const fullscreenBtn = document.getElementById('fullscreenBtn');
const downloadBtn = document.getElementById('downloadBtn');
const zoomSlider = document.getElementById('zoomSlider');
const zoomLevel = document.getElementById('zoomLevel');

// Event Listeners
prevBtn.addEventListener('click', goToPreviousPage);
nextBtn.addEventListener('click', goToNextPage);
fullscreenBtn.addEventListener('click', toggleFullscreen);
downloadBtn.addEventListener('click', downloadPDF);
zoomSlider.addEventListener('input', changeZoom);

// Keyboard Navigation
document.addEventListener('keydown', (e) => {
    if (e.key === 'ArrowLeft') goToPreviousPage();
    if (e.key === 'ArrowRight') goToNextPage();
});

// Load PDF
async function loadPDF(url) {
    try {
        console.log('Loading PDF from:', url);
        pdfDoc = await pdfjsLib.getDocument(url).promise;
        totalPages = pdfDoc.numPages;
        console.log('PDF loaded! Total pages:', totalPages);
        
        // Load first page
        loadPage(1);
        updatePageInfo();
    } catch (error) {
        console.error('Error loading PDF:', error);
        showError(error.message);
    }
}

// Load and display a page
async function loadPage(pageNum) {
    if (!pdfDoc || pageNum < 1 || pageNum > totalPages) return;

    try {
        const page = await pdfDoc.getPage(pageNum);
        const scale = (currentZoom / 100) * 2;
        const viewport = page.getViewport({ scale: scale });

        const canvas = document.createElement('canvas');
        const context = canvas.getContext('2d');
        canvas.width = viewport.width;
        canvas.height = viewport.height;

        await page.render({
            canvasContext: context,
            viewport: viewport
        }).promise;

        // Add animation class
        flipbookDiv.classList.remove('flip-animation');
        void flipbookDiv.offsetWidth; // Trigger reflow
        flipbookDiv.classList.add('flip-animation');

        // Replace content
        setTimeout(() => {
            flipbookDiv.innerHTML = '';
            const pageDiv = document.createElement('div');
            pageDiv.className = 'page';
            pageDiv.appendChild(canvas);
            flipbookDiv.appendChild(pageDiv);
            
            currentPage = pageNum;
            updatePageInfo();
        }, 300);

    } catch (error) {
        console.error('Error rendering page:', error);
    }
}

// Navigation
function goToNextPage() {
    if (currentPage < totalPages) {
        loadPage(currentPage + 1);
    }
}

function goToPreviousPage() {
    if (currentPage > 1) {
        loadPage(currentPage - 1);
    }
}

// Update page info and button states
function updatePageInfo() {
    pageInfo.textContent = `Página ${currentPage} de ${totalPages}`;
    prevBtn.disabled = currentPage === 1;
    nextBtn.disabled = currentPage === totalPages;
}

// Zoom
function changeZoom(e) {
    currentZoom = parseInt(e.target.value);
    zoomLevel.textContent = currentZoom + '%';
    loadPage(currentPage);
}

// Fullscreen
function toggleFullscreen() {
    if (!document.fullscreenElement) {
        flipbookDiv.requestFullscreen().catch(err => {
            alert('Erro ao ativar tela cheia: ' + err.message);
        });
    } else {
        document.exitFullscreen();
    }
}

// Download
function downloadPDF() {
    const link = document.createElement('a');
    link.href = pdfUrl;
    link.download = 'Embalagens Melamina.pdf';
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
}

// Error handler
function showError(message) {
    flipbookDiv.innerHTML = `
        <div style="
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100%;
            color: red;
            text-align: center;
            padding: 20px;
        ">
            <div>
                <h2>⚠️ Erro ao carregar PDF</h2>
                <p>${message}</p>
                <p style="font-size: 0.9em; color: #666; margin-top: 10px;">
                    Verifique se o arquivo "Embalagens Melamina.pdf" existe no repositório.
                </p>
            </div>
        </div>
    `;
}

// Initialize
console.log('Flipbook initializing...');
loadPDF(pdfUrl);
