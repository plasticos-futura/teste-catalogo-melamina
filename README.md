<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Catálogo Melamina</title>

<script src="https://cdn.jsdelivr.net/npm/page-flip/dist/js/page-flip.browser.min.js"></script>

<style>

body{
margin:0;
background:#1a1a1a;
display:flex;
justify-content:center;
align-items:center;
height:100vh;
}

#flipbook{
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

<div id="flipbook">

<div class="page"><img src="pages/page1.jpg"></div>
<div class="page"><img src="pages/page2.jpg"></div>
<div class="page"><img src="pages/page3.jpg"></div>
<div class="page"><img src="pages/page4.jpg"></div>
<div class="page"><img src="pages/page5.jpg"></div>
<div class="page"><img src="pages/page6.jpg"></div>
<div class="page"><img src="pages/page7.jpg"></div>
<div class="page"><img src="pages/page8.jpg"></div>
<div class="page"><img src="pages/page9.jpg"></div>
<div class="page"><img src="pages/page10.jpg"></div>
<div class="page"><img src="pages/page11.jpg"></div>
<div class="page"><img src="pages/page12.jpg"></div>
<div class="page"><img src="pages/page13.jpg"></div>
<div class="page"><img src="pages/page14.jpg"></div>
<div class="page"><img src="pages/page15.jpg"></div>
<div class="page"><img src="pages/page16.jpg"></div>
<div class="page"><img src="pages/page17.jpg"></div>
<div class="page"><img src="pages/page18.jpg"></div>
<div class="page"><img src="pages/page19.jpg"></div>
<div class="page"><img src="pages/page20.jpg"></div>
<div class="page"><img src="pages/page21.jpg"></div>
<div class="page"><img src="pages/page22.jpg"></div>
<div class="page"><img src="pages/page23.jpg"></div>
<div class="page"><img src="pages/page24.jpg"></div>

</div>

<script>

const pageFlip = new St.PageFlip(
document.getElementById("flipbook"),
{
width:500,
height:700,
size:"stretch",
minWidth:315,
maxWidth:1000,
minHeight:420,
maxHeight:1350,
maxShadowOpacity:0.5,
showCover:true,
mobileScrollSupport:true
}
);

pageFlip.loadFromHTML(
document.querySelectorAll(".page")
);

</script>

</body>

</html>
