
<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>عيد ميلاد سعيد!</title>
<style>
  body {
    font-family: Arial, sans-serif;
    text-align: center;
    background: linear-gradient(to bottom, #ffe6f0, #ffb3d1);
    padding: 50px;
    transition: 0.5s;
  }
  h1 {
    color: #d43f8d;
    font-size: 50px;
    margin-bottom: 20px;
  }
  p {
    font-size: 20px;
    color: #333;
    max-width: 600px;
    margin: 20px auto;
  }
  .cake {
    font-size: 120px;
    margin: 20px 0;
  }
  .confetti {
    position: fixed;
    width: 100%;
    height: 100%;
    pointer-events: none;
    overflow: hidden;
    top:0;
    left:0;
    z-index: 9999;
  }
  .confetti-piece {
    position: absolute;
    width: 10px;
    height: 10px;
    background: #ff69b4;
    opacity: 0.8;
    animation: fall 3s linear infinite;
  }
  @keyframes fall {
    0% {transform: translateY(-10px) rotate(0deg);}
    100% {transform: translateY(100vh) rotate(360deg);}
  }
  #content {
    display: none;
  }
  #login input[type="password"] {
    padding: 10px;
    font-size: 18px;
    margin-top: 20px;
  }
  #login button {
    padding: 10px 20px;
    font-size: 18px;
    margin-top: 10px;
    background-color: #d43f8d;
    color: white;
    border: none;
    border-radius: 8px;
    cursor: pointer;
  }
</style>
</head>
<body>

<div id="login">
  <h1>أدخل كلمة السر 🎉</h1>
  <input type="password" id="password" placeholder="كلمة السر">
  <br>
  <button onclick="checkPassword()">دخول</button>
</div>

<div id="content">
  <div class="confetti" id="confetti"></div>
  <div class="cake">🎂</div>
  <h1>عيد ميلاد سعيد!</h1>
  <p>
    مرحباً! حبيت أشاركك عيد ميلادك بطريقة حلوة، ويا رب كل سنة تكون سعيد ومحقق كل أحلامك. ❤️
  </p>
</div>

<script>
// ضع كلمة السر اللي تحبها هنا
const correctPassword = "mohamed123"; // دي كلمة السر، ممكن تغيرها لأي حاجة تحب

function checkPassword() {
  const input = document.getElementById('password').value;
  if(input === correctPassword){
    document.getElementById('login').style.display = 'none';
    document.getElementById('content').style.display = 'block';
    createConfetti();
  } else {
    alert("كلمة السر غلط 😅 حاول تاني");
  }
}

function createConfetti(){
  const confettiContainer = document.getElementById('confetti');
  for(let i=0; i<100; i++){
    const piece = document.createElement('div');
    piece.className = 'confetti-piece';
    piece.style.left = Math.random()*100 + 'vw';
    piece.style.backgroundColor = `hsl(${Math.random()*360}, 70%, 60%)`;
    piece.style.animationDuration = (2 + Math.random()*3) + 's';
    confettiContainer.appendChild(piece);
  }
}
</script>

</body>
</html>
