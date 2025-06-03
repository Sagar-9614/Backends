<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .calculator {
      background: #fff;
      padding: 20px 30px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }
    .display {
      width: 100%;
      height: 40px;
      font-size: 1.5em;
      margin-bottom: 15px;
      text-align: right;
      padding: 5px 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
      background: #e9ecef;
      box-sizing: border-box;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
    }
    .buttons button {
      font-size: 1.2em;
      padding: 15px;
      border: none;
      border-radius: 5px;
      background: #f0f0f0;
      cursor: pointer;
      transition: background 0.2s;
    }
    .buttons button.operator {
      background: #f7b731;
      color: #fff;
    }
    .buttons button.equal {
      background: #20bf6b;
      color: #fff;
      grid-column: span 2;
    }
    .buttons button.clear {
      background: #eb3b5a;
      color: #fff;
    }
    .buttons button:hover {
      background: #d1d8e0;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" class="display" id="display" disabled>
    <div class="buttons">
      <button onclick="clearDisplay()" class="clear">C</button>
      <button onclick="appendValue('(')">(</button>
      <button onclick="appendValue(')')">)</button>
      <button onclick="appendValue('/')" class="operator">÷</button>
      
      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('*')" class="operator">×</button>
      
      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('-')" class="operator">−</button>
      
      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="appendValue('+')" class="operator">+</button>
      
      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
      <button onclick="calculate()" class="equal">=</button>
    </div>
  </div>

  <script>
    function appendValue(val) {
      document.getElementById('display').value += val;
    }
    function clearDisplay() {
      document.getElementById('display').value = '';
    }
    function calculate() {
      try {
        let result = eval(document.getElementById('display').value);
        document.getElementById('display').value = result;
      } catch {
        document.getElementById('display').value = 'Error';
      }
    }
  </script>
</body>
</html>