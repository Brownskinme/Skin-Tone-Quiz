<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Brownskin.me Skin Tone Quiz</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- Fonts & Styles -->
  <link href="https://fonts.googleapis.com/css2?family=Allison&display=swap" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/jspdf"></script>
  <script src="https://cdn.emailjs.com/dist/email.min.js"></script>
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
    .question, .email-section {
      font-size: 1.2em;
      margin: 1em 0 0.5em;
    }
    .answers label {
      display: block;
      margin: 0.5em 0;
    }
    .btn {
      background-color: #7b3f00;
      color: #fff;
      border: none;
      padding: 0.7em 1.5em;
      font-size: 1em;
      cursor: pointer;
      border-radius: 6px;
      margin: 1em;
    }
    .results {
      margin-top: 2em;
      display: none;
    }
    .product-card {
      padding: 1em;
      border-top: 1px solid #eee;
      text-align: left;
    }
    .highlight {
      font-weight: bold;
      color: #7b3f00;
    }
    input[type="email"] {
      padding: 0.5em;
      width: 80%;
      border-radius: 5px;
      border: 1px solid #ccc;
      font-family: Arial, sans-serif;
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

      <div class="email-section">
        <label for="email">Enter your email to receive results:</label><br>
        <input type="email" id="email" name="email" required>
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
      <button class="btn" onclick="emailResults()">Email My Results</button>
      <button class="btn" onclick="downloadPDF()">Download PDF</button>
    </div>
  </div>

  <script>
    emailjs.init("YOUR_EMAILJS_USER_ID"); // Replace with your EmailJS public key

    const productSuggestions = {
      warm: { name: "SunGlow Bronze Foundation", price: 28, cost: 12 },
      cool: { name: "Rose Ice Dew Highlighter", price: 30, cost: 10 },
      neutral: { name: "Honey Velvet Skin Tint", price: 26, cost: 11 }
    };

    let selectedProduct = null;

    function calculateResult() {
      const selected = document.querySelector('input[name="undertone"]:checked');
      const email = document.getElementById('email').value;

      if (!selected || !email) {
        alert("Please select an option and provide your email.");
        return;
      }

      const value = selected.value;
      const product = productSuggestions[value];
      selectedProduct = product;

      const margin = ((product.price - product.cost) / product.price) * 100;

      document.getElementById("productName").innerText = product.name;
      document.getElementById("price").innerText = product.price.toFixed(2);
      document.getElementById("cost").innerText = product.cost.toFixed(2);
      document.getElementById("margin").innerText = `${margin.toFixed(1)}%`;

      document.getElementById("resultsBox").style.display = "block";
    }

    function emailResults() {
      const email = document.getElementById('email').value;
      if (!selectedProduct || !email) return;

      const templateParams = {
        to_email: email,
        product_name: selectedProduct.name,
        price: `$${selectedProduct.price.toFixed(2)}`,
        cost: `$${selectedProduct.cost.toFixed(2)}`,
        margin: `${((selectedProduct.price - selectedProduct.cost) / selectedProduct.price * 100).toFixed(1)}%`
      };

      emailjs.send("YOUR_SERVICE_ID", "YOUR_TEMPLATE_ID", templateParams)
        .then(() => alert("Results sent successfully!"))
        .catch(err => alert("Failed to send email. Error: " + err));
    }

    function downloadPDF() {
      if (!selectedProduct) return;
      const doc = new jsPDF();

      doc.setFontSize(20);
      doc.text("Brownskin.me Quiz Result", 20, 20);

      doc.setFontSize(14);
      doc.text(`Product: ${selectedProduct.name}`, 20, 40);
      doc.text(`Retail Price: $${selectedProduct.price.toFixed(2)}`, 20, 50);
      doc.text(`Estimated Cost: $${selectedProduct.cost.toFixed(2)}`, 20, 60);
      doc.text(`Projected Margin: ${((selectedProduct.price - selectedProduct.cost) / selectedProduct.price * 100).toFixed(1)}%`, 20, 70);

      doc.save("Brownskin_SkinTone_Result.pdf");
    }
  </script>
</body>
</html>

