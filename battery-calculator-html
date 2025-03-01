<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Battery Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f9;
      color: #333;
      margin: 0;
      padding: 20px;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
    }

    .container {
      background: #fff;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      padding: 20px;
      max-width: 400px;
      width: 100%;
    }

    h1 {
      text-align: center;
      margin-bottom: 20px;
      font-size: 1.8rem;
      color: #444;
    }

    .input-group {
      margin-bottom: 15px;
    }

    label {
      font-weight: bold;
      color: #555;
      display: block;
      margin-bottom: 5px;
    }

    .toggle-group {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .toggle-group select, input {
      flex: 1;
      margin-left: 10px;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
      font-size: 1rem;
    }

    button {
      width: 100%;
      padding: 10px;
      background: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 1rem;
      cursor: pointer;
      margin-top: 10px;
    }

    button:hover {
      background: #45a049;
    }

    .result {
      margin-top: 20px;
      font-weight: bold;
      text-align: center;
      font-size: 1.2rem;
      color: #333;
    }
  </style>
</head>
<body>

  <div class="container">
    <h1>Battery Calculator</h1>

    <!-- Input 1 -->
    <div class="input-group">
      <label for="input1-toggle">Input 1:</label>
      <div class="toggle-group">
        <select id="input1-type">
          <option value="voltage">Voltage (V)</option>
          <option value="capacity">Capacity (mAh)</option>
          <option value="energy">Energy (Wh)</option>
          <option value="current">Current (Amps)</option>
          <option value="time">Time (Hours)</option>
        </select>
        <input type="number" id="input1" placeholder="Enter value">
      </div>
    </div>

    <!-- Input 2 -->
    <div class="input-group">
      <label for="input2-toggle">Input 2:</label>
      <div class="toggle-group">
        <select id="input2-type">
          <option value="voltage">Voltage (V)</option>
          <option value="capacity">Capacity (mAh)</option>
          <option value="energy">Energy (Wh)</option>
          <option value="current">Current (Amps)</option>
          <option value="time">Time (Hours)</option>
        </select>
        <input type="number" id="input2" placeholder="Enter value">
      </div>
    </div>

    <!-- Output -->
    <div class="input-group">
      <label for="output-type">Desired Output:</label>
      <select id="output-type">
        <option value="energy">Energy (Wh)</option>
        <option value="voltage">Voltage (V)</option>
        <option value="capacity">Capacity (mAh)</option>
        <option value="current">Current (Amps)</option>
        <option value="time">Time (Hours)</option>
      </select>
    </div>

    <!-- Calculate Button -->
    <button onclick="calculate()">Calculate</button>

    <!-- Result -->
    <div class="result" id="result">Result will appear here</div>
  </div>

  <script>
    function calculate() {
      // Get selected types and input values
      const input1Type = document.getElementById('input1-type').value;
      const input2Type = document.getElementById('input2-type').value;
      const outputType = document.getElementById('output-type').value;
      const input1 = parseFloat(document.getElementById('input1').value);
      const input2 = parseFloat(document.getElementById('input2').value);

      if (isNaN(input1) || isNaN(input2)) {
        document.getElementById('result').innerText = "Please provide valid input values.";
        return;
      }

      let result = '';

      // Perform calculations based on inputs and output type
      if (outputType === 'energy' && input1Type === 'voltage' && input2Type === 'capacity') {
        const ah = input2 / 1000; // Convert mAh to Ah
        result = `Energy (Wh): ${(input1 * ah).toFixed(2)}`;
      } else if (outputType === 'voltage' && input1Type === 'energy' && input2Type === 'capacity') {
        const ah = input2 / 1000;
        result = `Voltage (V): ${(input1 / ah).toFixed(2)}`;
      } else if (outputType === 'capacity' && input1Type === 'energy' && input2Type === 'voltage') {
        const ah = input1 / input2;
        result = `Capacity (mAh): ${(ah * 1000).toFixed(2)}`;
      } else if (outputType === 'current' && input1Type === 'energy' && input2Type === 'time') {
        result = `Current (Amps): ${(input1 / input2).toFixed(2)}`;
      } else if (outputType === 'time' && input1Type === 'capacity' && input2Type === 'current') {
        const ah = input1 / 1000; // Convert mAh to Ah
        result = `Time (Hours): ${(ah / input2).toFixed(2)}`;
      } else {
        result = "Unsupported combination of inputs and output.";
      }

      // Display the result
      document.getElementById('result').innerText = result;
    }
  </script>

</body>
</html>
