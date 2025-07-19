`html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Our Love Story</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #fff0f5;
      text-align: center;
      padding: 20px;
    }

    h1 {
      font-size: 3em;
      color: crimson;
      position: relative;
      display: inline-block;
    }

    h1::after {
      content: "❤️";
      position: absolute;
      right: -40px;
      animation: heartbeat 1s infinite, glowPulse 2s infinite alternate;
    }

    @keyframes heartbeat {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.3); }
    }

    @keyframes glowPulse {
      from { text-shadow: 0 0 5px red; }
      to { text-shadow: 0 0 20px pink; }
    }

    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      margin-top: 30px;
    }

    .gallery-item {
      width: 150px;
      height: 150px;
      background: #ffe4e1;
      border: 2px solid pink;
      cursor: pointer;
      overflow: hidden;
      position: relative;
    }

    .gallery-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: none;
      animation: fadeIn 1s ease forwards;
      opacity: 0;
    }

    .gallery-item.active img {
      display: block;
      opacity: 1;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.9); }
      to { opacity: 1; transform: scale(1); }
    }

    textarea {
      width: 80%;
      height: 150px;
      margin-top: 30px;
      padding: 10px;
      font-size: 1em;
      border: 2px solid crimson;
      background: #fffafa;
      resize: vertical;
      animation: floatText 3s ease-in-out infinite alternate;
    }

    @keyframes floatText {
      from { transform: translateY(0px); }
      to { transform: translateY(-5px); }
    }
  </style>
</head>
<body>

  <h1>Our Love Story</h1>

  <div class="gallery">
    <div class="gallery-item"><img src="Screenshot_20250716_104734_Plus.jpg" alt="Moment 1"></div>
    <div class="gallery-item"><img src="img2.jpg" alt="Moment 2"></div>
    <div class="gallery-item"><img src="img3.jpg" alt="Moment 3"></div>
    <div class="gallery-item"><img src="img4.jpg" alt="Moment 4"></div>
    <div class="gallery-item"><img src="img5.jpg" alt="Moment 5"></div>
    <div class="gallery-item"><img src="img6.jpg" alt="Moment 6"></div>
    <div class="gallery-item"><img src="img7.jpg" alt="Moment 7"></div>
    <div class="gallery-item"><img src="img8.jpg" alt="Moment 8"></div>
    <div class="gallery-item"><img src="img9.jpg" alt="Moment 9"></div>
  </div>

  <textarea placeholder="Write your love letter here..."></textarea>

  <script>
    const items = document.querySelectorAll('.gallery-item');
    items.forEach(item => {
      item.addEventListener('click', () => {
        item.classList.toggle('active');
      });
    });
  </script>

</body>
</html>
`
