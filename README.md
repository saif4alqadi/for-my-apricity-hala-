<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<title>For Hala ❤️</title>

<style>
body {
  background: linear-gradient(135deg, #ff758c, #ff7eb3);
  font-family: 'Arial', sans-serif;
  text-align: center;
  height: 100vh;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  background: white;
  padding: 40px 30px;
  border-radius: 25px;
  box-shadow: 0 15px 30px rgba(0,0,0,0.25);
  width: 90%;
  max-width: 430px;
  max-height: 90vh;
  overflow-y: auto;
  position: relative;
}

h1 {
  color: #ff4d6d;
}

p {
  font-size: 16px;
  color: #333;
  line-height: 1.9;
}

.buttons {
  margin-top: 35px;
  position: relative;
  height: 160px;
}

button {
  padding: 14px 28px;
  font-size: 16px;
  border: none;
  border-radius: 30px;
  cursor: pointer;
}

#yes {
  background: #ff4d6d;
  color: white;
  position: absolute;
  left: 30px;
  bottom: 20px;
}

#no {
  background: #ddd;
  position: absolute;
  right: 30px;
  top: 20px;
}

.hidden {
  display: none;
}

.love {
  text-align: right;
  margin-top: 20px;
}
</style>
</head>

<body>

<div class="container" id="card">
  <h1>حبيبتي حلا 🤍</h1>
  <p>I have a question</p>
  <h2>Would you be my Valentine?</h2>

  <div class="buttons" id="buttonArea">
    <button id="yes">Yes 💖</button>
    <button id="no">No 🙃</button>
  </div>
</div>

<div class="container hidden" id="result">
  <h1>Best decision ever 🤍🤍🤍🤍</h1>
  <p style="color:#888; font-size:14px;">14 / 2 / 2026</p>

  <div class="love">
    <p>
      حبيبتي حلا 🤍<br><br>

      أنا أكثر إنسان محظوظ بالدنيا لأنه عندي إياكي…  
      عنجد ما بعرف شو عملت إشي منيح بحياتي عشان ربنا يخلي قلبك يحبني.<br><br>

      بتعرفي لما الواحد يكون عنده إشي غالي كثير؟  
      بضل يفكر فيه ويتطلع عليه طول الوقت؟  
      أنا هيك بحس معك والله.<br><br>

      يا روحي، أنا دايمًا بخاف عليكي من كثر ما بحبك،  
      وبعتبرك أغلى إشي بحياتي.<br><br>

      ما عندي بالدنيا أغلى منك،  
      ولا رح يكون في حدا بحنيتك عليّ 🤍<br><br>

      بوسة على جبينك 😚<br>
      بحبك كثير يا روحي والله 🤍
    </p>
  </div>

  <iframe id="song" width="100%" height="215"
    frameborder="0"
    allow="autoplay; encrypted-media"
    allowfullscreen>
  </iframe>
</div>

<script>
const noBtn = document.getElementById("no");
const yesBtn = document.getElementById("yes");
const card = document.getElementById("card");
const result = document.getElementById("result");
const buttonArea = document.getElementById("buttonArea");
const song = document.getElementById("song");

function moveButton() {
  const areaRect = buttonArea.getBoundingClientRect();
  const yesRect = yesBtn.getBoundingClientRect();

  let maxX = areaRect.width - noBtn.offsetWidth;
  let maxY = areaRect.height - noBtn.offsetHeight;

  let randomX, randomY;

  do {
    randomX = Math.random() * maxX;
    randomY = Math.random() * maxY;
  } 
  while (
    randomX < yesBtn.offsetLeft + yesBtn.offsetWidth &&
    randomX + noBtn.offsetWidth > yesBtn.offsetLeft &&
    randomY < yesBtn.offsetTop + yesBtn.offsetHeight &&
    randomY + noBtn.offsetHeight > yesBtn.offsetTop
  );

  noBtn.style.left = randomX + "px";
  noBtn.style.top = randomY + "px";
}

noBtn.addEventListener("mouseover", moveButton);
noBtn.addEventListener("click", function(e){
  e.preventDefault();
  moveButton();
});

yesBtn.addEventListener("click", () => {
  card.classList.add("hidden");
  result.classList.remove("hidden");

  // تشغيل الأغنية بعد الضغط
  song.src = "https://www.youtube.com/embed/450p7goxZqg?autoplay=1";
});
</script>

</body>
</html>
