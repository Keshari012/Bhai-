<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Small-Big Color Prediction Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f4;
            padding: 50px;
        }
        .result-box {
            font-size: 40px;
            font-weight: bold;
            color: white;
            width: 200px;
            height: 100px;
            line-height: 100px;
            margin: 20px auto;
            border-radius: 10px;
        }
        button {
            padding: 15px 30px;
            font-size: 18px;
            cursor: pointer;
            border: none;
            background-color: blue;
            color: white;
            border-radius: 5px;
        }
        .history {
            margin-top: 20px;
            font-size: 20px;
            text-align: center;
        }
    </style>
</head>
<body>

    <h1>Small-Big Color Prediction Game</h1>
    <p>Click "Start" to get a random result.</p>

    <div class="result-box" id="resultBox">?</div>

    <button onclick="generateResult()">Start</button>

    <h2>Result History</h2>
    <div class="history" id="history"></div>

    <script>
        function generateResult() {
            let randomValue = Math.random(); // 0 se 1 ke beech ek random number
            let resultBox = document.getElementById("resultBox");
            let historyDiv = document.getElementById("history");

            let resultText, color;
            if (randomValue < 0.5) {
                resultText = "Small";
                color = "green";
            } else {
                resultText = "Big";
                color = "red";
            }

            // Show result in box
            resultBox.innerText = resultText;
            resultBox.style.backgroundColor = color;

            // Add result to history
            let historyEntry = `<span style="color:${color}; font-weight:bold;">${resultText}</span>`;
            historyDiv.innerHTML = historyEntry + " | " + historyDiv.innerHTML;
        }
    </script>

</body>
</html>
