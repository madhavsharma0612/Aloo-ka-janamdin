# Aloo-ka-janamdin
Birthday website
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Aloo Ka Janamdin</title>
  <style>
    body {
      margin: 0;
      font-family: 'Georgia', serif;
      background: url('https://i.ibb.co/4S4F6Dc/parchment-bg.jpg');
      background-size: cover;
      text-align: center;
      color: #3e2f1c;
    }
    .page { display: none; padding: 40px; }
    .active { display: block; }
    button {
      padding: 12px 22px;
      border: none;
      background: #8b5e34;
      color: white;
      border-radius: 10px;
      cursor: pointer;
      font-size: 18px;
      font-family: 'Georgia', serif;
      box-shadow: 0 3px 6px rgba(0,0,0,0.25);
    }
    button:hover { background: #704826; }

    #cake { width: 260px; margin-top: 20px; border-radius: 12px; box-shadow: 0 4px 10px rgba(0,0,0,0.3); }
    #giftBox { width: 230px; cursor: pointer; border-radius: 12px; box-shadow: 0 4px 10px rgba(0,0,0,0.3); }

    h1, h2, h3 {
      font-family: 'Georgia', serif;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.2);
    }

    .book-frame {
      padding: 25px;
      border: 4px double #5c4328;
      background: rgba(255, 248, 235, 0.85);
      border-radius: 12px;
      width: 80%;
      margin: auto;
      box-shadow: 0 4px 10px rgba(0,0,0,0.3);
    }
  </style>
</head>
<body>

  <!-- PAGE 1: Ask Name -->
  <div id="page1" class="page active">
    <div class="book-frame">
      <h1 style="font-size:40px;">📖 Aloo Ka Janamdin – A Birthday Tale</h1>
      <p>Every great novel begins with a name…</p>
      <p>What should this story call you?</p>
      <input type="text" id="username" style="padding:10px; font-size:18px; border-radius:8px; border:2px solid #7a522a; font-family:Georgia;" />
      <br/><br/>
      <button onclick="goToPage2()">Turn the Page ➜</button>
    </div>
  </div>

  <!-- PAGE 2: Greeting -->
  <div id="page2" class="page">
    <div class="book-frame">
      <h1 id="greetText"></h1>
      <p>Another year, another beautiful chapter added to your story ✨</p>
      <button onclick="showPage('page3')">Turn the Page ➜</button>
    </div>
  </div>

  <!-- PAGE 3: Cake Page -->
  <div id="page3" class="page">
    <div class="book-frame">
      <h1>🎂 The Magical Novel Cake</h1>
      <img id="cake" src="https://i.ibb.co/QpZHJj1/novel-cake.png" alt="Cake with candles" />
      <br/><br/>
      <button onclick="blowCandles()">Blow Candles ✨</button>
      <br/><br/>
      <button onclick="showPage('page4')">Next Chapter ➜</button>
    </div>
  </div>

  <!-- PAGE 4: Gift Box -->
  <div id="page4" class="page">
    <div class="book-frame">
      <h1>🎁 A Mysterious Box Appears</h1>
      <p>Only the bravest reader dares to open it…</p>
      <img id="giftBox" src="https://i.ibb.co/H2t7V6M/book-gift.png" onclick="openGift()" />
      <h2 id="finalMessage" style="display:none; font-size:38px; color:#8b3b3b; margin-top:20px;"></h2>
    </div>
  </div>

  <script>
    function showPage(id) {
      document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
      document.getElementById(id).classList.add('active');
    }

    function goToPage2() {
      const name = document.getElementById('username').value.trim();
      const greet = document.getElementById('greetText');
      greet.innerText = name ? `Happy Birthday, ${name}! ✨` : "Happy Birthday, Aloo! ✨";
      showPage('page2');
    }

    function blowCandles() {
      document.getElementById('cake').src = "https://i.ibb.co/3d0T4B3/novel-cake-no-candles.png";
      alert("The candles go out… and a wish rises like a story's spark ✨");
    }

    function openGift() {
      document.getElementById('giftBox').src = "https://i.ibb.co/c6YKD1b/book-gift-open.png";
      document.getElementById('finalMessage').style.display = 'block';
      document.getElementById('finalMessage').innerText = "HAPPY BIRTHDAY ALOO 📚✨";
    }
  </script>

</body>
</html>

