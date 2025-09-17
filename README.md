<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>OOU Aggregate Calculator BY Senator Chris</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #0073e6, #00c6ff);
      color: #333;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .calculator {
      background: #fff;
      padding: 25px;
      border-radius: 15px;
      box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.2);
      text-align: center;
      width: 350px;
    }
    h2 {
      margin-bottom: 20px;
      color: #0073e6;
    }
    label {
      font-weight: bold;
      display: block;
      margin-top: 15px;
      text-align: left;
    }
    input {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 16px;
    }
    button {
      margin-top: 20px;
      padding: 12px 20px;
      font-size: 16px;
      font-weight: bold;
      background: #0073e6;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      background: #005bb5;
    }
    #result {
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
      color: green;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <h2>OOU Aggregate Calculator</h2>
    <label>JAMB Score:</label>
    <input type="number" id="jamb" max="400" placeholder="Enter JAMB score (0-400)">
    <label>Post-UTME Score:</label>
    <input type="number" id="post" max="100" placeholder="Enter Post-UTME score (0-100)">  
    <button onclick="calculate()">Calculate</button>
    
 <p id="result"></p>
  </div>

  <script>
    function calculate() {
      let jamb = document.getElementById("jamb").value;
      let post = document.getElementById("post").value;

      // Convert to numbers
      jamb = Number(jamb);
      post = Number(post);

      // Validation
      if (jamb > 400 || jamb < 0) {
        alert("⚠️ JAMB score must be between 0 and 400!");
        return;
      }
      if (post > 100 || post < 0) {
        alert("⚠️ Post-UTME score must be between 0 and 100!");
        return;
      }

      // Calculate aggregate
      let aggregate = (jamb / 400 * 60) + (post / 100 * 40);

      // Show result
      document.getElementById("result").innerText =
        "✅ Candidate's Aggregate: " + aggregate.toFixed(2);
    }
  </script>
</body>
</html>
