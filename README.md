<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FIND THE CASH WINNIPEG</title>
    <style>
        body {
            background-color: #000000;
            color: #ffffff;
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            position: relative;
        }
        .container {
            padding: 20px;
            background: rgba(255, 255, 255, 0.1);
            display: inline-block;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(255, 255, 255, 0.2);
            width: 90%;
            max-width: 400px;
            z-index: 2;
            position: relative;
        }
        #randomNumbers {
            font-size: 32px;
            font-weight: bold;
            margin-top: 20px;
            color: #ffffff;
            opacity: 0;
            transition: opacity 0.3s ease-in-out;
        }
        button {
            background: #ffffff;
            color: #000000;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            font-size: 18px;
            cursor: pointer;
            margin-top: 15px;
            width: 100%;
        }
        button:hover {
            background: #bbbbbb;
        }
        #dateTime {
            margin-top: 15px;
            font-size: 16px;
            color: #ffffff;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>FIND THE CASH WINNIPEG</h1>
        <div id="randomNumbers">Tap the button</div>
        <button onclick="generateUniqueNumber()">Generate Number</button>
        <button onclick="resetNumber()">Reset</button>
        <div id="dateTime"></div>
    </div>
    <script>
        let previousNumber = null;
        
        function generateUniqueNumber() {
            let newNumber;
            do {
                newNumber = Math.floor(Math.random() * 90) + 10;
            } while (newNumber === previousNumber);
            previousNumber = newNumber;
            let numberElement = document.getElementById("randomNumbers");
            numberElement.style.opacity = 0;  // Fade out
            setTimeout(function() {
                numberElement.textContent = `${newNumber}`;
                numberElement.style.opacity = 1;  // Fade in
            }, 300); // Wait for the fade-out transition to complete
        }

        function resetNumber() {
            let numberElement = document.getElementById("randomNumbers");
            numberElement.textContent = "Tap the button";
            numberElement.style.opacity = 1;
        }

        function updateDateTime() {
            let now = new Date();
            let dateTimeString = now.toLocaleString();
            document.getElementById("dateTime").textContent = dateTimeString;
        }
        
        setInterval(updateDateTime, 1000);
        updateDateTime(); // Initialize immediately
    </script>
</body>
</html>
