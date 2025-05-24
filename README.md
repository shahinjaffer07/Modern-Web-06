# Ex06 BMI Calculator

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
import React, { useState } from "react";
import "./App.css";

function App() {
  const [weight, setWeight] = useState("");
  const [height, setHeight] = useState("");
  const [bmi, setBmi] = useState(null);
  const [category, setCategory] = useState("");

  const calculateBMI = () => {
    if (weight && height) {
      const heightInMeters = height / 100;
      const bmiValue = (weight / (heightInMeters ** 2)).toFixed(2);
      setBmi(bmiValue);

      if (bmiValue < 18.5) setCategory("Underweight");
      else if (bmiValue < 25) setCategory("Normal weight");
      else if (bmiValue < 30) setCategory("Overweight");
      else setCategory("Obesity");
    }
  };

  return (
    <div className="main-container">
      <h1 className="title">BMI CALCULATOR</h1>
      <div className="form-container">
        <input
          type="number"
          placeholder="Height in cm"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
        />
        <input
          type="number"
          placeholder="Weight in Kg"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
        />
        <button onClick={calculateBMI}>CALCULATE BMI</button>
        {bmi && (
          <p className="bmi-result">
            Your BMI is {bmi} ({category})
          </p>
        )}
      </div>
    </div>
  );
}

export default App;

```
App.css
```
body {
  margin: 0;
  padding: 0;
  font-family: 'Segoe UI', sans-serif;
  background-color: #1e1e1e;
  color: white;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.main-container {
  text-align: center;
}

.title {
  font-size: 2rem;
  margin-bottom: 40px;
  color: white;
  letter-spacing: 1px;
}

.form-container {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 300px;
  margin: 0 auto;
}

input {
  padding: 15px;
  border: none;
  border-radius: 12px;
  background-color: #2e2e2e;
  color: #f1f1f1;
  font-size: 16px;
  box-shadow: inset 4px 4px 8px #1a1a1a, inset -4px -4px 8px #2e2e2e;
  outline: none;
}

input::placeholder {
  color: #888;
}

button {
  padding: 15px;
  border: none;
  border-radius: 12px;
  background-color: #1f1f1f;
  color: #00ff99;
  font-weight: bold;
  cursor: pointer;
  font-size: 16px;
  box-shadow: 4px 4px 8px #111, -4px -4px 8px #2a2a2a;
  transition: 0.3s ease;
}

button:hover {
  background-color: #2e2e2e;
}

.bmi-result {
  margin-top: 20px;
  font-size: 18px;
  color: #66ffcc;
}

```


## OUTPUT
![klo](https://github.com/user-attachments/assets/436df457-bb49-46a1-a2e2-1d1fabbb3f88)


## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
