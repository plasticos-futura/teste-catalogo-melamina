<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Melamina Catalogue</title>

<script src="https://cdn.jsdelivr.net/npm/page-flip/dist/js/page-flip.browser.min.js"></script>

<style>

body{
margin:0;
background:#1a1a1a;
font-family:Arial;
overflow:hidden;
}

#topbar{
position:fixed;
top:10px;
left:50%;
transform:translateX(-50%);
z-index:1000;
}

button{
padding:8px 14px;
margin:3px;
border:none;
background:#2c7be5;
color:white;
border-radius:4px;
cursor:pointer;
font-size:14px;
}

#container{
display:flex;
justify-content:center;
align-items:center;
height:100vh;
}

#book{
width:1000px;
height:700px;
}

.page{
background:white;
}

.page img{
width:100%;
height:100%;
object-fit:contain;
}

</style>

</head>

<body>

<div id="topbar">

<button onclick="prevPage()">◀</button>
<button onclick="nextPage()">▶</button>

<button onclick="zoomIn()">Zoom +</button>
<button onclick="zoomOut()">Zoom -</button>

<button onclick="toggleFullscreen()">Fullscreen</button>

</div>

<div id="container">

<div id="book"></div>

</div>

<script>

const pages = [

"pages/page1.jpg",
"pages/page2.jpg",
"pages/page3.jpg",
"pages/page4.jpg",
"pages/page5.jpg",
"pages/page6.jpg",
"pages/page7.jpg",
"pages/page8.jpg",
"pages/page9.jpg",
"pages/page10.jpg",
"pages/page11.jpg",
"pages/page12.jpg",
"pages/page13.jpg",
"pages/page14.jpg",
"pages/page15.jpg",
"pages/page16.jpg",
"pages/page17.jpg",
"pages/page18.jpg",
"pages/page19.jpg",
"pages/page20.jpg",
"pages/page21.jpg",
"pages/page22.jpg",
"pages/page23.jpg",
"pages/page24.jpg"

];

const pageFlip = new St.PageFlip(
document.getElementById("book"),
{
width:500,
height:700,
size:"stretch",
minWidth:300,
maxWidth:1000,
minHeight:400,
maxHeight:1200,
maxShadowOpacity:0.5,
showCover:true,
mobileScrollSupport:true
}
);

pageFlip.loadFromImages(pages);

function nextPage(){
pageFlip.flipNext();
}

function prevPage(){
pageFlip.flipPrev();
}

let zoom=1;

function zoomIn(){
zoom+=0.1;
document.getElementById("book").style.transform="scale("+zoom+")";
}

function zoomOut(){
zoom-=0.1;
document.getElementById("book").style.transform="scale("+zoom+")";
}

function toggleFullscreen(){

if(!document.fullscreenElement){
document.documentElement.requestFullscreen();
}else{
document.exitFullscreen();
}

}

</script>

</body>

</html>
