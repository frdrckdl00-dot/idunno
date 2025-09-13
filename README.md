<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Message for you</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background: linear-gradient(135deg, #fdfbfb, #ebedee);
      font-family: "Segoe UI", sans-serif;
    }

    .wrapper {
      text-align: center;
    }

    .question {
      font-size: 24px;
      margin-bottom: 20px;
      color: #333;
    }

    .gif {
      width: 250px;
      height: auto;
      border-radius: 12px;
      margin-bottom: 20px;
      transition: all 0.5s ease;
    }

    .btn-group {
      display: flex;
      justify-content: center;
      gap: 20px;
    }

    button {
      padding: 10px 20px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .yes-btn {
      background: #4caf50;
      color: white;
    }

    .no-btn {
      background: #f44336;
      color: white;
      position: relative;
      transition: all 0.4s ease;
    }

    /* Bounce animation for gif */
    .bounce {
      animation: bounce 1s infinite;
    }

    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-15px); }
    }
  </style>
</head>
<body>
  <div class="wrapper">
    <h2 class="question">You like me?</h2>
    <img class="gif" alt="gif" src="https://raw.githubusercontent.com/DzarelDeveloper/Img/main/gifyou.webp">
    <div class="btn-group">
      <button class="yes-btn">Yes</button>
      <button class="no-btn">No</button>
    </div>
  </div>

  <script>
    const noBtn = document.querySelector('.no-btn');
    const yesBtn = document.querySelector('.yes-btn');
    const gif = document.querySelector('.gif');
    const question = document.querySelector('.question');
    let clickCount = 0;

    // No button runs away and fades
    noBtn.addEventListener('click', () => {
      clickCount++;
      const randomX = Math.floor(Math.random() * 200 - 100);
      const randomY = Math.floor(Math.random() * 100 - 50);
      noBtn.style.transform = `translate(${randomX * clickCount}px, ${randomY * clickCount}px)`;
      noBtn.style.opacity = 1 - (clickCount * 0.2);

      if (clickCount >= 5) {
        noBtn.style.display = 'none';
      }
    });

    // Yes button changes gif + text
    yesBtn.addEventListener('click', () => {
      question.textContent = "I like you too Araaaaaaaa :)";
      gif.src = "stitch.gif";  // your local Stitch gif file
      gif.classList.add("bounce");
    });
  </script>
</body>
</html>
