---
toc: true
comments: false
layout: post
title: calculator 
type: hacks
courses: { compsci: {week: 1} }
---
<html>
<head>
    <title>Calculator</title>
    <style>
        .calculator {
            width: 300px;
            margin: 0 auto;
        }
        input[type="text"] {
            width: 100%;
            padding: 10px;
            font-size: 18px;
            margin-bottom: 10px;
        }
        button {
            width: 50px;
            height: 50px;
            font-size: 18px;
            margin: 5px;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" readonly>
        <button onclick="appendToDisplay('1')">1</button>
        <button onclick="appendToDisplay('2')">2</button>
        <button onclick="appendToDisplay('3')">3</button>
        <button onclick="appendToDisplay('+')">+</button>
        <button onclick="appendToDisplay('4')">4</button>
        <button onclick="appendToDisplay('5')">5</button>
        <button onclick="appendToDisplay('6')">6</button>
        <button onclick="appendToDisplay('-')">-</button>
        <button onclick="appendToDisplay('7')">7</button>
        <button onclick="appendToDisplay('8')">8</button>
        <button onclick="appendToDisplay('9')">9</button>
        <button onclick="appendToDisplay('*')">x</button>
        <button onclick="appendToDisplay('0')">0</button>
        <button onclick="calculate()">=</button>
        <button onclick="clearDisplay()">C</button>
        <button onclick="appendToDisplay('/')">/</button>
    </div>
    
    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function calculate() {
            var expression = document.getElementById('display').value;
            var result = eval(expression);
            document.getElementById('display').value = result;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }
    </script>
</body>
</html>
