const yesBtn=document.getElementById("yesBtn");
const noBtn=document.getElementById("noBtn");
const tease=document.getElementById("tease");
const question=document.getElementById("question");
const letter=document.getElementById("letter");
const music=document.getElementById("music");
const musicBtn=document.getElementById("musicBtn");

let noClicks=0;
const messages=["Точно? 🥺","Подумай ещё раз 😭","НЕТ убегает от тебя 😂","Ну пожалуйстааа 💗","Ты знаешь правильный ответ 😌","Ладно, последний шанс ❤️"];

function moveNoButton(){
  const area=document.querySelector(".buttons");
  const maxX=Math.max(0,area.clientWidth-noBtn.offsetWidth);
  const maxY=70;
  noBtn.style.position="absolute";
  noBtn.style.left=(Math.random()*maxX)+"px";
  noBtn.style.top=(Math.random()*maxY)+"px";
}
noBtn.addEventListener("pointerenter",()=>{if(window.matchMedia("(hover:hover)").matches)moveNoButton()});
noBtn.addEventListener("pointerdown",(e)=>{e.preventDefault();noClicks++;tease.textContent=messages[Math.min(noClicks-1,messages.length-1)];moveNoButton()});

yesBtn.addEventListener("click",()=>{
 question.classList.remove("active");
 letter.classList.add("active");
 window.scrollTo(0,0);
 for(let i=0;i<35;i++)setTimeout(createHeart,i*55);
});

musicBtn.addEventListener("click",async()=>{
 if(music.paused){
   try{await music.play();musicBtn.textContent="⏸ Пауза";}
   catch{document.getElementById("musicText").textContent="Положи music.mp3 в папку сайта 🎵";}
 }else{music.pause();musicBtn.textContent="🎵 Наша песня";}
});

function createHeart(){
 const h=document.createElement("span");
 h.className="heart";
 h.textContent=["♥","♡","💗","💕","✨"][Math.floor(Math.random()*5)];
 h.style.left=Math.random()*100+"vw";
 h.style.fontSize=14+Math.random()*22+"px";
 h.style.animationDuration=5+Math.random()*6+"s";
 document.querySelector(".hearts").appendChild(h);
 setTimeout(()=>h.remove(),12000);
}
setInterval(createHeart,900);
