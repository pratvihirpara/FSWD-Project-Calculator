# FSWD-Project-Calculator
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Calculator</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #222;
        color: #eee;
    }
    .calculator {
        width: 300px;
        margin: 50px auto;
        background-color: #444;
        border-radius: 5px;
        box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        padding: 20px;
        box-sizing: border-box;
        border: 2px solid #333;
    }
    .calculator input[type="text"] {
        width: calc(100% - 10px);
        margin-bottom: 10px;
        padding: 10px;
        border-radius: 5px;
        border: 1px solid #666;
        background-color: #555;
        color: #eee;
    }
    .calculator button {
        width: calc(25% - 5px);
        padding: 10px;
        margin: 5px;
        border-radius: 5px;
        border: none;
        cursor: pointer;
        background-color: #777;
        color: #eee;
        font-size: 18px;
    }
    .calculator button.operator {
        background-color: #f0ad4e;
        color: #222;
    }
    .calculator button.clear {
        background-color: #d9534f;
        color: #222;
    }
</style>
</head>
<body>

<div class="calculator">
    <input type="text" id="display" readonly>
    <button onclick="clearDisplay()" class="clear">C</button>
    <button onclick="appendToDisplay('7')">7</button>
    <button onclick="appendToDisplay('8')">8</button>
    <button onclick="appendToDisplay('9')">9</button>
    <button onclick="appendToDisplay('/')">/</button>
    <button onclick="appendToDisplay('4')">4</button>
    <button onclick="appendToDisplay('5')">5</button>
    <button onclick="appendToDisplay('6')">6</button>
    <button onclick="appendToDisplay('')"></button>
    <button onclick="appendToDisplay('1')">1</button>
    <button onclick="appendToDisplay('2')">2</button>
    <button onclick="appendToDisplay('3')">3</button>
    <button onclick="appendToDisplay('-')">-</button>
    <button onclick="appendToDisplay('0')">0</button>
    <button onclick="appendToDisplay('.')">.</button>
    <button onclick="calculate()" style="background-color: #5cb85c; color: #222;">=</button>
    <button onclick="appendToDisplay('+')" class="operator">+</button>
</div>

<script>
    function appendToDisplay(value) {
        document.getElementById('display').value += value;
    }

    function clearDisplay() {
        document.getElementById('display').value = '';
    }

    function calculate() {
        let expression = document.getElementById('display').value;
        try {
            let result = eval(expression);
            document.getElementById('display').value = result;
        } catch (error) {
            document.getElementById('display').value = 'Error';
        }
    }
</script>

</body>
</html>
