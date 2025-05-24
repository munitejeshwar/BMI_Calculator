# Ex06 BMI Calculator
## Date:

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
```
## bmicalclater.jsx:
import React, { useState } from 'react';

const BMICalculator = () => {
  const [weight, setWeight] = useState('');
  const [height, setHeight] = useState('');
  const [bmi, setBmi] = useState(null);
  const [category, setCategory] = useState('');

  const calculateBMI = () => {
    if (!weight || !height) return;
    const h = height / 100;
    const result = (weight / (h * h)).toFixed(2);
    setBmi(result);

    if (result < 18.5) setCategory('Underweight');
    else if (result < 24.9) setCategory('Normal weight');
    else if (result < 29.9) setCategory('Overweight');
    else setCategory('Obesity');
  };

  return (
    <div className="page">
      <h2>BMI Calculator</h2>
      <input
        type="number"
        placeholder="Weight (kg)"
        value={weight}
        onChange={(e) => setWeight(e.target.value)}
      />
      <input
        type="number"
        placeholder="Height (cm)"
        value={height}
        onChange={(e) => setHeight(e.target.value)}
      />
      <button onClick={calculateBMI}>Calculate</button>

      {bmi && (
        <div className="result">
          <p><strong>BMI:</strong> {bmi}</p>
          <p><strong>Category:</strong> {category}</p>
        </div>
      )}
    </div>
  );
};

export default BMICalculator;

```
## home.jsx:
```
import React from 'react';
import { Link } from 'react-router-dom';

const Home = () => {
  return (
    <div className="page">
      <h1>Welcome to BMI Calculator</h1>
      <Link to="/calculate">
        <button>Go to Calculator</button>
      </Link>
    </div>
  );
};

export default Home;
```
## App.css:
```
body {
  background: linear-gradient(to bottom right, #dfe9f3, #ffffff);
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.page {
  text-align: center;
  margin-top: 60px;
  padding: 20px;
}

input {
  padding: 12px;
  margin: 12px;
  width: 220px;
  border-radius: 8px;
  border: 1px solid #ccc;
  font-size: 16px;
}

button {
  padding: 12px 25px;
  background: #28a745;
  border: none;
  color: white;
  font-size: 16px;
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.3s;
}

button:hover {
  background: #218838;
}

.result {
  margin-top: 25px;
  font-size: 18px;
  color: #333;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/4289097a-62e2-4f25-8c5e-92782f7344dc)



## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
