<!doctype html>
<html lang="fr">
<head>
  <meta charset="utf-8">
  <title>MathBoost</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #0b0f1a;
      color: #eef2ff;
    }
    .wrap {
      max-width: 900px;
      margin: auto;
      padding: 20px;
    }
    .card {
      background: #111a2f;
      border-radius: 14px;
      padding: 16px;
      margin-bottom: 12px;
    }
    h1, h2 {
      margin-top: 0;
    }
    button {
      padding: 10px 14px;
      border-radius: 10px;
      border: none;
      cursor: pointer;
      background: #7c3aed;
      color: white;
      font-size: 16px;
    }
    input {
      width: 100%;
      padding: 8px;
      border-radius: 8px;
      border: 1px solid #555;
      background: #0b1226;
      color: white;
      margin-bottom: 10px;
    }
  </style>
</head>

<body>
  <div class="wrap">

    <div class="card">
      <h1>📘 MathBoost</h1>
      <p>Application de révision maths – objectif 20/20 💪</p>
    </div>

    <div class="card">
      <h2>Exercice</h2>
      <p id="question">Clique sur “Commencer”</p>
      <input id="answer" placeholder="Ta réponse">
      <button onclick="check()">Corriger</button>
      <p id="result"></p>
      <br>
      <button onclick="start()">Commencer</button>
    </div>

  </div>

  <script>
    const exercices = [
      { q: "5x - 7 = 3x + 9", a: "8" },
      { q: "2(x + 4) = 18", a: "5" },
      { q: "3/4 + 5/8", a: "11/8" }
    ];

    let current;

    function start() {
      current = exercices[Math.floor(Math.random() * exercices.length)];
      document.getElementById("question").innerText = current.q;
      document.getElementById("result").innerText = "";
      document.getElementById("answer").value = "";
    }

    function check() {
      const v = document.getElementById("answer").value.trim();
      if (v === current.a) {
        document.getElementById("result").innerText = "✅ Bonne réponse !";
      } else {
        document.getElementById("result").innerText =
          "❌ Faux. Réponse : " + current.a;
      }
    }
  </script>
</body>
</html>
