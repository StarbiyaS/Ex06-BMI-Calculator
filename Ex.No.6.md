# Ex06 BMI Calculator
## Date: 14-11-2025

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM
App.jsx
```
import React, { useState } from 'react';
import './App.css';

function App() {
  const [weight, setWeight] = useState('');
  const [height, setHeight] = useState('');
  const [bmi, setBmi] = useState(null);
  const [message, setMessage] = useState('');

  const calculateBMI = () => {
    if (weight && height) {
      const heightInMeters = height / 100;
      const calculatedBMI = (weight / (heightInMeters * heightInMeters)).toFixed(2);
      setBmi(calculatedBMI);
      getBMICategory(calculatedBMI);
    } else {
      alert('Please enter valid height and weight.');
    }
  };

  const getBMICategory = (bmi) => {
    if (bmi < 18.5) setMessage('Underweight');
    else if (bmi >= 18.5 && bmi < 24.9) setMessage('Normal weight');
    else if (bmi >= 25 && bmi < 29.9) setMessage('Overweight');
    else setMessage('Obese');
  };

  const resetFields = () => {
    setWeight('');
    setHeight('');
    setBmi(null);
    setMessage('');
  };

  return (
    <div className="container">
      <h1>BMI Calculator</h1>
      <div className="input-group">
        <label>Weight (kg):</label>
        <input
          type="number"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
          placeholder="Enter weight"
        />
      </div>
      <div className="input-group">
        <label>Height (cm):</label>
        <input
          type="number"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
          placeholder="Enter height"
        />
      </div>
      <button onClick={calculateBMI}>Calculate</button>
      <button className="reset" onClick={resetFields}>Reset</button>
      
      {bmi && (
        <div className="result">
          <h2>Your BMI: {bmi}</h2>
          <p className="message">{message}</p>
        </div>
      
      )}
      <div>
        <footer> Done By:STARBIYA S</footer>
      </div>
    </div>
  );
}

export default App;
```

App.css
```
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f0f4f8;
  margin: 0;
  padding: 0;
}

.container {
  max-width: 400px;
  margin: 100px auto;
  padding: 30px;
  background-color: white;
  border-radius: 12px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  text-align: center;
}

h1 {
  margin-bottom: 20px;
  color: #333;
}

.input-group {
  margin-bottom: 20px;
  text-align: left;
}

.input-group label {
  display: block;
  margin-bottom: 5px;
  font-weight: 500;
}

.input-group input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border: 2px solid #ddd;
  border-radius: 8px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  margin: 10px 5px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  background-color: #007bff;
  color: white;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #0056b3;
}

button.reset {
  background-color: #6c757d;
}

button.reset:hover {
  background-color: #5a6268;
}

.result {
  margin-top: 30px;
  padding: 20px;
  border-radius: 8px;
  background-color: #f8f9fa;
}

.message {
  font-size: 18px;
  font-weight: bold;
  color: #444;
}
```

## OUTPUT

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4d835e12-0fb4-41ee-9376-321eaf6af986" />

## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
