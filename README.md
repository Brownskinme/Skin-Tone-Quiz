<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Brownskin.me Skin Tone Quiz</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- Google Font -->
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
      font-size: 1.3em;
      margin: 1em 0 0.5em;
    }

    .answers label {
      display: block;
      margin: 0.5em 0;
      cursor: pointer;
      font-size: 1em;
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

    .step {
      display: none;
    }

    .step.active {
      display: block;
    }
  </style>
</head>
<body>
  <div class="quiz-container">
    <h1>Find Your Skin Tone Match</h1>
    <form id="quizForm">
      <div class="step active" id="step1">
        <div class="question">1. What undertone does your skin have?</div>
        <div class="answers">
          <label><input type="radio" name="undertone" value="warm"> Warm (golden, peachy)</label>
          <label><input type="radio" name="undertone" value="cool"> Cool (pink, red, bluish)</label>
          <label><input type="radio" name="undertone" value="neutral"> Neutral (a mix)</label>
        </div>
      </div>

      <div class="step" id="step2">
        <div class="question">2. How does your skin react to the sun?</div>
        <div class="answers">
          <label><input type="radio" name="sun" value="tans"> Tans easily</label>
          <label><input type="radio" name="sun" value="burns"> Burns easily</label>
          <label><input type="radio" name="sun" value="both"> Both burn and tan</label>
        </div>
      </div>

      <div class="step" id="step3">
        <div class="question">3. What color are the veins on your wrist?</div>
        <div class="answers">
          <label><input type="radio" name="veins" value="green"> Green</label>
          <label><input type="radio" name="veins" value="blue"> Blue or purple</label>
          <label><input type="radio" name="veins" value="unclear"> Hard to tell</label>
        </div>
      </div>

      <button type="button" class="btn" onclick="nextStep()">Next</button>
    </form>

    <div class="results" id="resultsBox">
      <h2>Your Suggested Product</h2>
      <div class="product-card" id="productCard">
        <h3 id="productName">—</h3>
        <p><span class="highlight">Retail Price:</span> $<span id="price">0.00</span></p>
        <p><span class="highlight">Estimated Cost:</span> $<span id="cost">0.00</span></p>
        <p><span class="highlight">Projected Margin:</span> <span id="margin">0%</span></p>
      </div>
      <button class="btn" onclick="restartQuiz()">Try Again</button>
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

    let currentStep = 1;

    function nextStep() {
      const stepEl = document.getElementById(`step${currentStep}`);
      const selected = stepEl.querySelector('input[type="radio"]:checked');
      if (!selected) {
        alert("Please select an option to proceed.");
        return;
      }

      stepEl.classList.remove("active");
      currentStep++;

      if (currentStep <= 3) {
        document.getElementById(`step${currentStep}`).classList.add("active");
      } else {
        showResults();
      }
    }

    function showResults() {
      const undertone = document.querySelector('input[name="undertone"]:checked')?.value;
      const sun = document.querySelector('input[name="sun"]:checked')?.value;
      const veins = document.querySelector('input[name="veins"]:checked')?.value;

      // Basic logic (could be replaced with ML/API)
      let match = undertone;

      // Adjust neutrality if veins are unclear or sun behavior is mixed
      if (veins === "unclear" || sun === "both") match = "neutral";

      const product = productSuggestions[match];
      const margin = ((product.price - product.cost) / product.price) * 100;

      document.getElementById("productName").innerText = product.name;
      document.getElementById("price").innerText = product.price.toFixed(2);
      document.getElementById("cost").innerText = product.cost.toFixed(2);
      document.getElementById("margin").innerText = `${margin.toFixed(1)}%`;

      document.getElementById("resultsBox").style.display = "block";
    }

    function restartQuiz() {
      currentStep = 1;
      document.getElementById("resultsBox").style.display = "none";
      const steps = document.querySelectorAll(".step");
      steps.forEach(step => step.classList.remove("active"));
      document.getElementById("step1").classList.add("active");
      document.getElementById("quizForm").reset();
    }
  </script>
</body>
</html>
