<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Temperature Converter</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color:lightblue;
            
            margin:solid
        }

        #converter {
            max-width: 400px;
            margin: auto;
            background-color:yellow;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        label {
           
            margin-bottom: 10px;
            padding:15px;
        }

        input {
            width: 100%;
            padding: 8px;
            margin-bottom: 15px;
            box-sizing: border-box;
        }

        button {
            background-color: green;
            color: #fff;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        button:hover {
            background-color: #0056b3;
        }
        #para1{ 
        
        height:330px;
        width:200px;
        background-color:white;
        position:absolute;
        top:0px;
        left:20px;
        border:10px solid green;
        }
        #para2{ 
        
        height:330px;
        width:200px;
        background-color:white;
        position:absolute;
        top:0px;
        right:20px;
        border:10px solid green;
        }
        #para3{
        height:150px;
        width:400px;
        background-color:white;
        position:absolute;
        top:400px;
        left:450px;
        border:10px solid green;
        }

        header {
            background-color:lightgreen;
            padding: 10px;
            color: red;

        #result {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div id="converter">
        <header>
        <h1>Temperature Converter</h1>
    </header>
      

        <label for="tempInput">Enter Temperature:</label>
        <input type="number" id="tempInput" placeholder="Enter temperature" />

        <label for="fromUnit">From:</label>
        <select id="fromUnit">
            <option value="celsius">Celsius</option>
            <option value="fahrenheit">Fahrenheit</option>
            <option value="kelvin">Kelvin</option>
        </select>

        <label for="toUnit">To:</label>
        <select id="toUnit">
            <option value="celsius">Celsius</option>
            <option value="fahrenheit">Fahrenheit</option>
            <option value="kelvin">Kelvin</option>
        </select>

        <button onclick="convertTemperature()">Convert</button>

        <div id="result"></div>
    </div>
    <p id="para1">Celsius, scale based on 0° for the freezing point of water and 100° for the boiling point of water. Invented in 1742 by the Swedish astronomer Anders Celsius, it is sometimes called the centigrade scale because of the 100-degree interval between the defined points. The following formula can be used to convert a temperature from its representation on the Fahrenheit (°F) scale to the Celsius (°C) value:
   <br>°C = 5/9(°F − 32).</p>
     <p id="para2">
Fahrenheit is a scale for measuring temperature, in which water freezes at 32 degrees and boils at 212 degrees. It is represented by the symbol ° F. the temperature was already above 100 ° F..
A temperature interval of 1 °F was equal to an interval of 5⁄9 degrees Celsius. With the Fahrenheit and Celsius scales defined by the kelvin, this relationship was preserved, a temperature interval of 1 °F being equal to an interval of 5⁄9 K and of 5⁄9 °C.</p>
     <p id="para3">
Why is Kelvin 273? A precise description og the Kelvin scale 
The scale was invented by Lord Kelvin who saw the need for a scale where absolute zero was the null point, which means that 0 K is the lowest possible temperature = -273,15 °C. The Kelvin Scale uses Celsius for its unit increment, meaning that +1 K is the same as +1 °C</p>
    <script>
        function convertTemperature() {
            var tempInput = document.getElementById('tempInput').value;
            var fromUnit = document.getElementById('fromUnit').value;
            var toUnit = document.getElementById('toUnit').value;

            var result;

            if (fromUnit === 'celsius') {
                if (toUnit === 'fahrenheit') {
                    result = (tempInput * 9/5) + 32;
                } else if (toUnit === 'kelvin') {
                    result = parseFloat(tempInput) + 273.15;
                } else {
                    result = tempInput;
                }
            } else if (fromUnit === 'fahrenheit') {
                if (toUnit === 'celsius') {
                    result = (tempInput - 32) * 5/9;
                } else if (toUnit === 'kelvin') {
                    result = (tempInput - 32) * 5/9 + 273.15;
                } else {
                    result = tempInput;
                }
            } else if (fromUnit === 'kelvin') {
                if (toUnit === 'celsius') {
                    result = tempInput - 273.15;
                } else if (toUnit === 'fahrenheit') {
                    result = (tempInput - 273.15) * 9/5 + 32;
                } else {
                    result = tempInput;
                }
            }

            document.getElementById('result').innerHTML = `Result: ${result.toFixed(2)} ${toUnit}`;
        }
    </script>

</body>
</html>
