<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Brownskin.me Skin Tone Quiz</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- Allison Script Font -->
  <link href="https://fonts.googleapis.com/css2?family=Allison&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Allison', cursive;
      background-color: #fff8f4;
      margin: 0;
      padding: 0;
      color: #333;
      text-align: center;
    }

    .quiz-container {
      max-width: 700px;
      margin: 2em auto;
      background: white;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      padding: 2em;
    }

    h1 {
      font-size: 2.5em;
      margin-bottom: 0.5em;
      color: #7b3f00;
    }

    .question {
      font-size: 1.2em;
      margin: 1em 0 0.5em;
    }

    .answers label {
      display: block;
      margin: 0.5em 0;
      cursor: pointer;
    }

    .btn {
      background-color: #7b3f00;
      color: #fff;
      border: none;
      padding: 0.7em 1.5em;
      font-size: 1em;
      cursor: pointer;
      border-radius: 6px;
      margin-top: 1.5em;
    }

    .results {
      margin-top: 2em;
      display: none;
    }

    .product-card {
      margin-top: 1em;
      padding: 1em;
      border-top: 1px solid #eee;
      text-align: left;
    }

    .product-card h3 {
      margin: 0.2em 0;
    }

    .highlight {
      font-weight: bold;
      color: #7b3f00;
    }
  </style>
</head>
<body>
  <div class="quiz-container">
    <h1>Find Your Skin Tone Match</h1>
    <form id="quizForm">
      <div class="question">1. What undertone does your skin have?</div>
      <div class="answers">
        <label><input type="radio" name="undertone" value="warm"> Warm (golden, peachy)</label>
        <label><input type="radio" name="undertone" value="cool"> Cool (pink, red, bluish)</label>
        <label><input type="radio" name="undertone" value="neutral"> Neutral (a mix of warm and cool)</label>
      </div>
      <button type="button" class="btn" onclick="calculateResult()">Show My Match</button>
    </form>

    <div class="results" id="resultsBox">
      <h2>Your Suggested Product</h2>
      <div class="product-card" id="productCard">
        <h3 id="productName">—</h3>
        <p><span class="highlight">Retail Price:</span> $<span id="price">0.00</span></p>
        <p><span class="highlight">Estimated Cost:</span> $<span id="cost">0.00</span></p>
        <p><span class="highlight">Projected Margin:</span> <span id="margin">0%</span></p>
      </div>
    </div>
  </div>

  <script>
    const productSuggestions = {
      warm: {
        name: "SunGlow Bronze Foundation",
        price: 28,
        cost: 12
      },
      cool: {
        name: "Rose Ice Dew Highlighter",
        price: 30,
        cost: 10
      },
      neutral: {
        name: "Honey Velvet Skin Tint",
        price: 26,
        cost: 11
      }
    };

    function calculateResult() {
      const selected = document.querySelector('input[name="undertone"]:checked');
      if (!selected) {
        alert("Please select an option.");
        return;
      }

      const value = selected.value;
      const product = productSuggestions[value];

      document.getElementById("productName").innerText = product.name;
      document.getElementById("price").innerText = product.price.toFixed(2);
      document.getElementById("cost").innerText = product.cost.toFixed(2);

      const margin = ((product.price - product.cost) / product.price) * 100;
      document.getElementById("margin").innerText = `${margin.toFixed(1)}%`;

      document.getElementById("resultsBox").style.display = "block";
    }
  </script>
</body>
</html>

