<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy New Year Muskan 💗</title>

<style>
body{
    margin:0;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(135deg,#ff758c,#ff7eb3);
    color:white;
    text-align:center;
    overflow:hidden;
}
.page{
    display:none;
    height:100vh;
    padding:30px;
    opacity:0;
    transition: opacity 1s ease;
}
.active{
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    opacity:1;
}
button{
    padding:12px 25px;
    font-size:18px;
    border:none;
    border-radius:30px;
    cursor:pointer;
    margin:10px;
}
.yes{ background:#00ffcc; }
.no{ background:#ff4d4d; color:white; }

.heart{
    position:fixed;
    animation: float linear infinite;
    color:#ffccd5;
}
@keyframes float{
    0%{bottom:-10px; opacity:0;}
    50%{opacity:1;}
    100%{bottom:110%; opacity:0;}
}

/* Scrollbar styling for page 4 */
#p4::-webkit-scrollbar { width:6px; }
#p4::-webkit-scrollbar-thumb { background:#ff7eb3; border-radius:3px; }

/* Scroll hint */
.scroll-hint{
    font-size:14px;
    margin-top:10px;
    opacity:0.8;
    animation: blink 1.5s infinite;
}
@keyframes blink{ 0%,100%{opacity:0.8;} 50%{opacity:0;} }

iframe.spotify-player{
    border-radius:12px;
    margin-top:15px;
}
</style>
</head>

<body>

<!-- PAGE 1 -->
<div class="page active" id="p1">
    <h1>🎉 Happy New Year Muskan 🫂🫂💗</h1>

    <!-- Spotify Embed -->
    <iframe class="spotify-player" 
        src="https://open.spotify.com/embed/track/0Y6YW1552df031DjV8qBHv" 
        width="300" height="80" 
        frameborder="0" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture">
    </iframe>

    <button onclick="nextPage(2)">Next 💖</button>
</div>

<!-- PAGE 2 -->
<div class="page" id="p2">
    <h2>How much I love you baccha 🫂❤</h2>
    <h1 id="percent">1%</h1>
    <h2 id="infinity" style="display:none;">∞</h2>
    <p id="text" style="display:none;">I love you until infinity 💗</p>
    <button onclick="nextPage(3)">Next 💞</button>
</div>

<!-- PAGE 3 -->
<div class="page" id="p3">
    <h2>Do you love me? 💗</h2>
    <div>
        <button class="yes" onclick="nextPage(4)">Yes 🫂</button>
        <button class="no" onclick="noLove()">No 💔</button>
    </div>
    <p id="drama"></p>
</div>

<!-- PAGE 4 -->
<div class="page" id="p4" style="overflow-y:auto; text-align:left;">
<p style="max-width:900px; font-size:17px; line-height:1.6;">
Mere liye aaj ka din bohot accha tha..subah ki starting waise hi hui jaise pehle jab ham relationship me aye the tab hua karti thi...🫂💗 Or aajka din bohot pyara tha idk tumhare liye kaisa tha but mere liye bohot pyara tha wo alag baat hai aaj me thoda busy tha or thoda tum to utni baat nahi hui but subah bohot acche se baat hui wo bohot pyari cheez thi or ykw mussu 🫂🫂💗 aaj tum mere liye rose leke ayi..mujhe pehli bar kisi ne rose diya (isse pehle family cousin sister friend kisi ne nahi diya) 🫂💗 ye meri life ka first rose tha or mujhe nahi pata tha mai kaise react karu to me bas blush kare ja raha tha mujhe kuch nahi bolna tha me bas khush hona cahta tha 🫂🫂💗 ... [your full text continues]
</p>
<div class="scroll-hint">⬇ Scroll for more ⬇</div>
<button onclick="nextPage(5)">Next 💗</button>
</div>

<!-- PAGE 5 -->
<div class="page" id="p5">
    <h1>I love you Muskan 🫂❤</h1>
    <h2>Thank you for choosing me 💗</h2>
</div>

<script>
function nextPage(n){
    document.querySelectorAll('.page').forEach(p=>{
        p.classList.remove('active');
    });
    document.getElementById('p'+n).classList.add('active');
}

let i=1;
let interval=setInterval(()=>{
    document.getElementById("percent").innerText=i+"%";
    i++;
    if(i>100){
        clearInterval(interval);
        document.getElementById("percent").style.display="none";
        document.getElementById("infinity").style.display="block";
        document.getElementById("text").style.display="block";
    }
},40);

function noLove(){
    document.getElementById("drama").innerText =
    "💔 Agar tumne NO bola hota to shayad dil thoda toot jata... par phir bhi main tumse pyar karta rehta 💗";
}

// Improved heart animation
setInterval(()=>{
    let h=document.createElement("div");
    h.className="heart";
    h.innerText="💗";
    h.style.left=Math.random()*100+"%";
    h.style.fontSize=(10 + Math.random()*20)+"px";
    h.style.animationDuration=(4 + Math.random()*4)+"s";
    document.body.appendChild(h);
    setTimeout(()=>h.remove(),6000);
},200);
</script>

</body>
</html>
