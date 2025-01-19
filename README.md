<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interest Calculator</title>
    <style>
        /* Your CSS code goes here */

        .container {
            width: 50%;
            margin: 50px auto;
            padding: 20px;
            background-color: white;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }

        h1 {
            text-align: center;
            color: #333;
        }

        .image-container {
            text-align: center;
            margin-bottom: 20px;
        }

        .image-container img {
            max-width: 100%;
            height: auto;
            border-radius: 8px;
        }

        label {
            font-size: 16px;
            display: block;
            margin: 10px 0 5px;
        }

        input[type="number"], input[type="button"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }

        .result {
            margin-top: 20px;
            padding: 10px;
            background-color: #f0f0f0;
            border-radius: 5px;
            font-size: 18px;
        }

        .button-container {
            display: flex;
            justify-content: space-between;
        }

        input[type="button"] {
            width: 48%;
            background-color: #4CAF50;
            color: white;
            cursor: pointer;
            border: none;
        }

        input[type="button"]:hover {
            background-color: #45a049;
        }

        .reset-btn {
            background-color: #f44336;
        }

        .reset-btn:hover {
            background-color: #da190b;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="image-container">
            <!-- Replace this URL with your image source -->
            <img src="calculator_image.jpg" alt="Person calculating interest" />
        </div>
        <h1>Interest Calculator</h1>
        <label for="principal">Principal Amount</label>
        <input type="number" id="principal" placeholder="Enter principal amount">
        
        <label for="rate">Interest Rate (%)</label>
        <input type="number" id="rate" placeholder="Enter interest rate">
        
        <label for="time">Time (years)</label>
        <input type="number" id="time" placeholder="Enter time in years">
        
        <div class="button-container">
            <input type="button" value="Calculate" onclick="calculateInterest()">
            <input type="button" value="Reset" class="reset-btn" onclick="resetFields()">
        </div>

        <div class="result" id="result">
            <!-- Calculation result will be displayed here -->
        </div>
    </div>

    <script>
        function calculateInterest() {
            const principal = document.getElementById("principal").value;
            const rate = document.getElementById("rate").value;
            const time = document.getElementById("time").value;

            if (!principal || !rate || !time) {
                alert("Please fill in all fields!");
                return;
            }

            const interest = (principal * rate * time) / 100;
            const totalAmount = parseFloat(principal) + parseFloat(interest);

            const resultElement = document.getElementById("result");
            resultElement.innerHTML = `
                <p>Interest: $${interest.toFixed(2)}</p>
                <p>Total Amount: $${totalAmount.toFixed(2)}</p>
            `;
        }

        function resetFields() {
            document.getElementById("principal").value = "";
            document.getElementById("rate").value = "";
            document.getElementById("time").value = "";
            document.getElementById("result").innerHTML = "";
        }
    </script>
</body>
</html>
