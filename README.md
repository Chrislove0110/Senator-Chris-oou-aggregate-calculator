<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>OOU Aggregate Calculator by Senator Chris</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(to right, #00c6ff, #0072ff);
      color: #333;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      padding: 10px;
    }
    .container {
      background: #fff;
      padding: 25px;
      border-radius: 12px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
      width: 100%;
      max-width: 400px;
      text-align: center;
    }
    h2 {
      margin-bottom: 20px;
      color: #0072ff;
      font-size: 1.5rem;
    }
    label {
      display: block;
      margin-top: 12px;
      font-weight: bold;
      text-align: left;
    }
    input {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 1rem;
    }
    button {
      margin-top: 20px;
      padding: 12px;
      background: #0072ff;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-weight: bold;
      width: 100%;
      font-size: 1rem;
    }
    button:hover {
      background: #005bb5;
    }
    #result {
      margin-top: 20px;
      font-size: 1.2rem;
      font-weight: bold;
      color: #333;
    }
    /* Responsive text */
    @media (max-width: 600px) {
      h2 {
        font-size: 1.2rem;
      }
      button {
        font-size: 0.95rem;
      }
      input {
        font-size: 0.95rem;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>OOU Aggregate Calculator by Senator Chris</h2>
    <label for="jamb">JAMB Score:</label>
    <input type="number" id="jamb" max="400" placeholder="Enter JAMB score (0-400)">

    <label for="post">Post-UTME Score:</label>
    <input type="number" id="post" max="100" placeholder="Enter Post-UTME score (0-100)">

    <button onclick="calculate()">Calculate</button>
    <p id="result"></p>
  </div>

  <script>
    function calculate() {
      let jamb = document.getElementById("jamb").value;
      let post = document.getElementById("post").value;

      if (jamb === "" || post === "") {
        document.getElementById("result").innerText = "⚠️ Please enter both scores.";
        return;
      }

      if (jamb < 0 || jamb > 400 || post < 0 || post > 100) {
        document.getElementById("result").innerText = "⚠️ Invalid input. JAMB (0-400), Post-UTME (0-100).";
        return;
      }

      let aggregate = (jamb / 400 * 60) + (post / 100 * 40);
      document.getElementById("result").innerText =
        "Candidate's Aggregate: " + aggregate.toFixed(2);
    }
  </script>
</body>
</html>
