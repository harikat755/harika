<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday Srihari 🎉</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family: 'Poppins', sans-serif;
}

body{
  min-height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background: linear-gradient(270deg,
    red, orange, yellow, green, cyan, blue, violet);
  background-size: 1200% 1200%;
  animation: rainbow 15s ease infinite;
  color:#fff;
}

@keyframes rainbow {
  0%{background-position:0% 50%}
  50%{background-position:100% 50%}
  100%{background-position:0% 50%}
}

.card{
  width:92%;
  max-width:420px;
  background:rgba(0,0,0,0.35);
  border-radius:22px;
  padding:22px;
  text-align:center;
  box-shadow:0 20px 45px rgba(0,0,0,0.5);
  position:relative;
  overflow:hidden;
}

h1{
  font-size:2.1rem;
  color:#ffe066;
}

h2{
  font-size:1.1rem;
  margin:8px 0 15px;
}

.cake{
  font-size:4rem;
  animation:bounce 1.5s infinite;
}

@keyframes bounce{
  0%,100%{transform:translateY(0)}
  50%{transform:translateY(-12px)}
}

p{
  font-size:0.95rem;
  line-height:1.6;
  margin:15px 0;
}

.photo-box{
  margin:15px 0;
}

.photo-box img{
  width:100%;
  max-height:220px;
  object-fit:cover;
  border-radius:15px;
  display:none;
  border:2px solid #fff;
}

input[type="file"]{
  margin-top:10px;
  color:#fff;
}

.btn{
  margin-top:15px;
  padding:12px 24px;
  border-radius:30px;
  border:none;
  background:linear-gradient(135deg,#ff7a18,#ffb347);
  font-weight:600;
  cursor:pointer;
}

.btn:hover{
  transform:scale(1.05);
}

.hearts span{
  position:absolute;
  bottom:-20px;
  animation:float 6s linear infinite;
  font-size:22px;
}

@keyframes float{
  0%{transform:translateY(0);opacity:0}
  10%{opacity:1}
  100%{transform:translateY(-120vh);opacity:0}
}

.qr{
  margin-top:15px;
}

footer{
  margin-top:12px;
  font-size:0.75rem;
  opacity:0.8;
}
</style>
</head>

<body>

<div class="card">
  <div class="hearts" id="hearts"></div>

  <h1>Happy Birthday Srihari 🎉</h1>
  <h2>Bangaram 💗 | Bava 😘</h2>

  <div class="cake">🎂🫂</div>

  <p>
    My dear <b>Bangaram Srihari</b>,  
    you are not just special, you are everything 💗  
    May your life be filled with love, success, laughter  
    and endless happiness 🫂😘  
    Always stay smiling, my Bava 💖
  </p>

  <!-- Photo Upload -->
  <div class="photo-box">
    <img id="preview">
    <input type="file" accept="image/*" onchange="loadPhoto(event)">
  </div>

  <!-- Music -->
  <audio controls autoplay loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3">
  </audio>

  <br>
  <button class="btn" onclick="surprise()">Click for Surprise 🎁</button>

  <!-- QR Code -->
  <div class="qr">
    <p>Scan to Open This Wish 💝</p>
    <img id="qrImage" width="140">
  </div>

  <footer>
    Made with 💗 for Srihari
  </footer>
</div>

<script>
/* Floating emojis */
const hearts = document.getElementById("hearts");
const emojis = ["💗","😘","🫂"];

function createHeart(){
  const span = document.createElement("span");
  span.innerText = emojis[Math.floor(Math.random()*emojis.length)];
  span.style.left = Math.random()*100 + "vw";
  span.style.animationDuration = (4+Math.random()*3)+"s";
  hearts.appendChild(span);
  setTimeout(()=>span.remove(),7000);
}
setInterval(createHeart,500);

/* Photo preview */
function loadPhoto(event){
  const img = document.getElementById("preview");
  img.src = URL.createObjectURL(event.target.files[0]);
  img.style.display = "block";
}

/* Surprise message */
function surprise(){
  alert("💖 Happy Birthday Srihari! Bangaram Bava forever 🫂😘");
}

/* QR Code for current link */
const qr = document.getElementById("qrImage");
const link = window.location.href;
qr.src = "https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=" + encodeURIComponent(link);
</script>

</body>
</html>
