<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Proposal</title>
  <style>
    body {
      background-color: #ffe6f0;
      font-family: 'Arial', sans-serif;
      text-align: center;
      padding: 50px;
      overflow: hidden;
    }

    h1 {
      color: #ff69b4;
    }

    .button {
      background-color: #ffb6c1;
      border: none;
      color: white;
      padding: 15px 30px;
      margin: 10px;
      font-size: 18px;
      border-radius: 10px;
      cursor: pointer;
      position: relative;
      transition: transform 0.3s ease;
    }

    #page2 {
      display: none;
    }

    .hearts::before {
      content: "♥ ♥ ♥ ♥ ♥ ♥ ♥ ♥ ♥ ♥";
      position: fixed;
      width: 100%;
      top: 0;
      left: 0;
      font-size: 24px;
      color: rgba(255, 105, 180, 0.2);
      animation: float 5s infinite linear;
      z-index: -1;
    }

    @keyframes float {
      0% { transform: translateY(0); }
      100% { transform: translateY(100vh); }
    }
  </style>
</head>
<body>
  <div class="hearts"></div>

  <div id="page1">
    <h1>Hello my only love and darling?</h1>
    <p>If you love me, please tap YES</p>
    <button id="yesBtn" class="button">YES</button>
    <button id="noBtn" class="button">NO</button>
    <p id="message"></p>
  </div>

  <div id="page2">
    <h1>I love youuu love,<br>Pirme</h1>
  </div>

  <script>
    let yesBtn = document.getElementById("yesBtn");
    let noBtn = document.getElementById("noBtn");
    let message = document.getElementById("message");
    let page1 = document.getElementById("page1");
    let page2 = document.getElementById("page2");

    let yesCount = 0;

    function dodge(btn) {
      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 100);
      btn.style.position = "absolute";
      btn.style.left = `${x}px`;
      btn.style.top = `${y}px`;
    }

    yesBtn.addEventListener("click", () => {
      yesCount++;
      if (yesCount === 1) {
        message.innerText = "It seems that you didn’t love me sincerely huh?";
        dodge(yesBtn);
      } else if (yesCount === 2) {
        message.innerText = "Oops maybe not?";
        dodge(yesBtn);
      } else {
        page1.style.display = "none";
        page2.style.display = "block";
      }
    });

    noBtn.addEventListener("click", () => {
      message.innerText = "No, you can’t unlove me. You are mine!";
      dodge(noBtn);
    });
  </script>
</body>
</html>
