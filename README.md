<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pok Ta Pok</title>

  <link href="https://fonts.googleapis.com/css2?family=Fondamento&display=swap" rel="stylesheet">

  <style>
    body {
      margin: 0;
      font-family: 'Fondamento', cursive;
      color: white;
      text-align: center;
      background:
        linear-gradient(rgba(0,0,0,0.55), rgba(0,0,0,0.8)),
        url('https://i.pinimg.com/736x/e8/9b/06/e89b064afa3eba3274049bc8c1b5c77c.jpg');
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      min-height: 100vh;
    }

    .container {
      margin-top: 12vh;
      padding: 20px;
    }

    h1.ptk-hero-title {
      font-size: 4rem;
      line-height: 1;
      margin-bottom: 12px;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 0.15em;
      flex-wrap: wrap;
      text-shadow: 0 0 10px rgba(0,0,0,0.8), 2px 2px 10px black;
    }

    .ptk-title-pok,
    .ptk-title-ta,
    .ptk-title-pok2 {
      color: #f4d58d;
      text-shadow:
        0 0 5px rgba(244, 213, 141, 0.4),
        0 0 12px rgba(244, 213, 141, 0.3),
        2px 2px 10px rgba(0,0,0,0.9);
    }

    .ptk-title-ball {
      color: #ffffff;
      font-size: 0.7em;
      line-height: 1;
      transform: translateY(-0.05em);
      text-shadow:
        0 0 6px rgba(255,255,255,0.5),
        0 0 12px rgba(255,255,255,0.3),
        2px 2px 10px rgba(0,0,0,0.9);
    }

    .ptk-hero-sub {
      font-size: 1.4rem;
      margin-top: 0;
      margin-bottom: 28px;
      text-shadow: 1px 1px 8px black;
    }

    p {
      font-size: 1.2rem;
      text-shadow: 1px 1px 6px black;
    }

    input {
      padding: 10px;
      font-size: 1.2rem;
      width: 80px;
      margin: 10px;
      border-radius: 10px;
      border: none;
      text-align: center;
    }

    button {
      padding: 12px 20px;
      font-size: 1.2rem;
      border-radius: 12px;
      border: none;
      cursor: pointer;
      background: #6b3fa0;
      color: white;
      font-family: 'Fondamento', cursive;
      box-shadow: 0 4px 12px rgba(0,0,0,0.4);
    }

    button:hover {
      transform: scale(1.03);
    }

    .result {
      font-size: 3rem;
      margin-top: 20px;
      text-shadow: 2px 2px 10px black;
    }

    @media (max-width: 700px) {
      h1.ptk-hero-title {
        font-size: 2.8rem;
      }

      .ptk-hero-sub {
        font-size: 1.1rem;
      }
    }
  </style>
</head>

<body>
  <div class="container">
    <h1 class="ptk-hero-title">
      <span class="ptk-title-pok">Pok</span>
      <span class="ptk-title-ball" aria-hidden="true">●</span>
      <span class="ptk-title-ta">Ta</span>
      <span class="ptk-title-pok2">Pok</span>
    </h1>

    <p class="ptk-hero-sub">Do you have what it takes?</p>

    <p>Choose your range:</p>
    <input id="min" type="number" placeholder="Min">
    <input id="max" type="number" placeholder="Max">
    <br>

    <button onclick="roll()">Roll Fate</button>

    <div class="result" id="result">?</div>
  </div>

  <script>
    function roll() {
      let min = parseInt(document.getElementById("min").value);
      let max = parseInt(document.getElementById("max").value);

      if (isNaN(min) || isNaN(max) || min >= max) {
        document.getElementById("result").textContent = "Invalid range";
        return;
      }

      let num = Math.floor(Math.random() * (max - min + 1)) + min;
      document.getElementById("result").textContent = num;
    }
  </script>
</body>
</html>
