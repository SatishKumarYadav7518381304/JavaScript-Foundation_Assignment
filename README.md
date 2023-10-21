# JavaScript-Foundation_Assignment


Quers 1   Password Validator

Ans   Creating a password validator is a common task for web applications to ensure that users choose secure and strong passwords. Here's an example of a simple password validator using JavaScript. In this example, we'll check if the password meets the following criteria:

At least 8 characters long.
Contains at least one lowercase letter.
Contains at least one uppercase letter.
Contains at least one digit (0-9).
Contains at least one special character (e.g., !, @, #, $, etc.).
HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Password Validator</title>
</head>
<body>
  <h1>Password Validator</h1>
  <label for="password">Enter your password: </label>
  <input type="password" id="password" oninput="validatePassword()">
  <p id="message"></p>
</body>
</html>

JavaScript (script.js):

function validatePassword() {
  // Get the password input element and the message element
  const passwordInput = document.getElementById('password');
  const messageElement = document.getElementById('message');

  // Regular expressions to check for password criteria
  const lengthRegex = /.{8,}/;
  const lowercaseRegex = /[a-z]/;
  const uppercaseRegex = /[A-Z]/;
  const digitRegex = /\d/;
  const specialCharRegex = /[^a-zA-Z0-9]/;

  // Check if the password meets all criteria
  const password = passwordInput.value;
  const isLengthValid = lengthRegex.test(password);
  const hasLowercase = lowercaseRegex.test(password);
  const hasUppercase = uppercaseRegex.test(password);
  const hasDigit = digitRegex.test(password);
  const hasSpecialChar = specialCharRegex.test(password);

  // Generate a message based on the validation results
  if (isLengthValid && hasLowercase && hasUppercase && hasDigit && hasSpecialChar) {
    messageElement.textContent = 'Password is strong and valid.';
  } else {
    messageElement.textContent = 'Password does not meet the criteria. Please try again.';
  }
}


In this code, we use regular expressions to check if the password meets the required criteria. The validatePassword function is called every time the user inputs text into the password field. The validation message is displayed accordingly.

This is a basic example, and you can customize the validation criteria to meet your specific security requirements.

Ques 2   Calculator

Ans  Creating a simple calculator using HTML, CSS, and JavaScript is a common project. Here's an example of a basic calculator that can perform addition, subtraction, multiplication, and division:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Simple Calculator</title>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" class="display" disabled>
    <div class="buttons">
      <button onclick="clearDisplay()">C</button>
      <button onclick="appendToDisplay('7')">7</button>
      <button onclick="appendToDisplay('8')">8</button>
      <button onclick="appendToDisplay('9')">9</button>
      <button onclick="appendToDisplay('+')">+</button>
      <button onclick="appendToDisplay('4')">4</button>
      <button onclick="appendToDisplay('5')">5</button>
      <button onclick="appendToDisplay('6')">6</button>
      <button onclick="appendToDisplay('-')">-</button>
      <button onclick="appendToDisplay('1')">1</button>
      <button onclick="appendToDisplay('2')">2</button>
      <button onclick="appendToDisplay('3')">3</button>
      <button onclick="appendToDisplay('*')">*</button>
      <button onclick="appendToDisplay('0')">0</button>
      <button onclick="appendToDisplay('.')">.</button>
      <button onclick="calculateResult()">=</button>
      <button onclick="appendToDisplay('/')">/</button>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>

CSS (styles.css):

body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background-color: #f0f0f0;
}

.calculator {
  background-color: #fff;
  border: 1px solid #ccc;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  width: 300px;
  text-align: center;
  border-radius: 5px;
  padding: 10px;
}

.display {
  width: 100%;
  padding: 5px;
  font-size: 24px;
  border: none;
  background-color: #f0f0f0;
  text-align: right;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 5px;
  margin-top: 10px;
}

button {
  font-size: 20px;
  padding: 10px;
  background-color: #007bff;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

JavaScript (script.js):

let currentDisplay = '';

function appendToDisplay(value) {
  currentDisplay += value;
  document.getElementById('display').value = currentDisplay;
}

function clearDisplay() {
  currentDisplay = '';
  document.getElementById('display').value = '';
}

function calculateResult() {
  try {
    currentDisplay = eval(currentDisplay).toString();
    document.getElementById('display').value = currentDisplay;
  } catch (error) {
    document.getElementById('display').value = 'Error';
    currentDisplay = '';
  }
}

This is a simple calculator with a user interface where you can enter numbers and operators to perform basic arithmetic operations. The JavaScript code handles appending input to the display, clearing the display, and evaluating the result when the equals button is clicked. The design is minimal, and you can customize it further to suit your preferences.




Ques 4 Color Mixer

Ans  Creating a color mixer that allows users to blend colors is a fun project. Here's a basic example of a color mixer using HTML, CSS, and JavaScript. In this example, users can select two colors and see the resulting mixture:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Color Mixer</title>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <div class="color-mixer">
    <div class="color-picker">
      <label for="color1">Select Color 1:</label>
      <input type="color" id="color1">
      <label for="color2">Select Color 2:</label>
      <input type="color" id="color2">
    </div>
    <div class="color-display">
      <p>Mixed Color:</p>
      <div id="mixed-color"></div>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>

CSS (styles.css):

body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background-color: #f0f0f0;
}

.color-mixer {
  background-color: #fff;
  border: 1px solid #ccc;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  width: 300px;
  text-align: center;
  border-radius: 5px;
  padding: 20px;
}

.color-picker {
  margin-bottom: 20px;
}

.color-picker label {
  display: block;
  margin-bottom: 5px;
}

.color-display {
  text-align: center;
}

#mixed-color {
  width: 100px;
  height: 100px;
  margin: 0 auto;
  border: 2px solid #ccc;
  border-radius: 50%;
}


JavaScript (script.js):

const color1Input = document.getElementById('color1');
const color2Input = document.getElementById('color2');
const mixedColorDiv = document.getElementById('mixed-color');

function updateMixedColor() {
  const color1 = color1Input.value;
  const color2 = color2Input.value;

  mixedColorDiv.style.backgroundColor = mixColors(color1, color2);
}

function mixColors(color1, color2) {
  return `rgb(${mixColorChannel(color1, color2, 'r')}, ${mixColorChannel(color1, color2, 'g')}, ${mixColorChannel(color1, color2, 'b')})`;
}

function mixColorChannel(color1, color2, channel) {
  const c1 = parseInt(color1.substr(1, 2), 16);
  const c2 = parseInt(color2.substr(1, 2), 16);
  const mixed = Math.floor((c1 + c2) / 2);

  return channel === 'r' ? mixed : channel === 'g' ? mixed : mixed;
}

color1Input.addEventListener('input', updateMixedColor);
color2Input.addEventListener('input', updateMixedColor);

// Initialize the mixed color
updateMixedColor();


In this example, users can pick two colors using the color inputs, and a mixed color is displayed in the circle below. The JavaScript code handles updating the mixed color when the inputs change. The mixColors function calculates the average of the RGB values of the two selected colors. This is a basic example, and you can extend it to handle more advanced color mixing and blending options.

Ques 4  Highest Marks

Ans  
Creating a program to find the highest marks among a set of students' marks is a common task. Below is an example of a simple JavaScript program that finds the highest marks among a set of student scores:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Highest Marks Finder</title>
</head>
<body>
  <h1>Highest Marks Finder</h1>
  <p>Enter student marks separated by commas:</p>
  <input type="text" id="marksInput">
  <button onclick="findHighestMarks()">Find Highest Marks</button>
  <p id="result"></p>
  <script src="script.js"></script>
</body>
</html>


JavaScript (script.js):

function findHighestMarks() {
  const marksInput = document.getElementById('marksInput').value;
  const marksArray = marksInput.split(',').map(Number);

  if (marksArray.length === 0 || marksArray.some(isNaN)) {
    document.getElementById('result').textContent = 'Invalid input. Please enter valid student marks.';
  } else {
    const highestMarks = Math.max(...marksArray);
    document.getElementById('result').textContent = 'The highest marks are: ' + highestMarks;
  }
}


In this program, users can enter student marks separated by commas in the input field. When they click the "Find Highest Marks" button, the JavaScript code will split the input into an array of marks, convert them to numbers, and then find and display the highest marks among them.

This is a basic example, and you can expand upon it to handle more complex scenarios, such as finding the highest marks for multiple subjects or multiple students.

Ques 5 Capitalize

Ans Capitalizing the first letter of a string is a common text manipulation task. Here's a simple JavaScript program that capitalizes the first letter of a string:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Capitalize First Letter</title>
</head>
<body>
  <h1>Capitalize First Letter</h1>
  <p>Enter a string:</p>
  <input type="text" id="inputString">
  <button onclick="capitalizeFirstLetter()">Capitalize</button>
  <p id="result"></p>
  <script src="script.js"></script>
</body>
</html>

JavaScript (script.js):

function capitalizeFirstLetter() {
  const inputString = document.getElementById('inputString').value;
  const capitalizedString = capitalize(inputString);
  document.getElementById('result').textContent = 'Capitalized string: ' + capitalizedString;
}

function capitalize(str) {
  if (str.length === 0) {
    return str;
  }
  return str.charAt(0).toUpperCase() + str.slice(1);
}


In this program, users can enter a string in the input field, and when they click the "Capitalize" button, the JavaScript code will capitalize the first letter of the string and display the result.

This is a basic example, and you can expand on it to handle more complex text formatting tasks or capitalize multiple words within a sentence


Ques 6 Vowel Counter

Creating a JavaScript program to count the number of vowels in a given string is a common task. Here's a simple example of a vowel counter program:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Vowel Counter</title>
</head>
<body>
  <h1>Vowel Counter</h1>
  <p>Enter a string:</p>
  <input type="text" id="inputString">
  <button onclick="countVowels()">Count Vowels</button>
  <p id="result"></p>
  <script src="script.js"></script>
</body>
</html>

JavaScript (script.js):

function countVowels() {
  const inputString = document.getElementById('inputString').value;
  const vowelCount = getVowelCount(inputString);
  document.getElementById('result').textContent = `Number of vowels: ${vowelCount}`;
}

function getVowelCount(str) {
  const vowels = 'aeiouAEIOU';
  let count = 0;

  for (let i = 0; i < str.length; i++) {
    if (vowels.includes(str[i])) {
      count++;
    }
  }

  return count;
}

n this program, users can enter a string in the input field, and when they click the "Count Vowels" button, the JavaScript code will count the number of vowels (both lowercase and uppercase) in the string and display the result.

This is a basic example, and you can expand on it to count vowels in more complex strings or consider additional variations of vowels (e.g., accented characters).

Ques 7  Remove Duplicates

Ans  Creating a JavaScript program to remove duplicates from an array or a string is a common task. Here's a simple example of a program to remove duplicates from an array and a string:

Removing Duplicates from an Array:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Remove Duplicates</title>
</head>
<body>
  <h1>Remove Duplicates from an Array</h1>
  <p>Enter a list of items separated by commas:</p>
  <input type="text" id="inputArray">
  <button onclick="removeArrayDuplicates()">Remove Duplicates</button>
  <p id="arrayResult"></p>
  <script src="script.js"></script>
</body>
</html>


JavaScript (script.js) for removing array duplicates:

function removeArrayDuplicates() {
  const inputArray = document.getElementById('inputArray').value.split(',').map(item => item.trim());
  const uniqueArray = Array.from(new Set(inputArray));
  document.getElementById('arrayResult').textContent = 'Array without duplicates: ' + uniqueArray.join(', ');
}


Removing Duplicates from a String:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Remove Duplicates</title>
</head>
<body>
  <h1>Remove Duplicates from a String</h1>
  <p>Enter a string:</p>
  <input type="text" id="inputString">
  <button onclick="removeStringDuplicates()">Remove Duplicates</button>
  <p id="stringResult"></p>
  <script src="script.js"></script>
</body>
</html>

JavaScript (script.js) for removing string duplicates:

function removeStringDuplicates() {
  const inputString = document.getElementById('inputString').value;
  const uniqueString = removeDuplicatesFromString(inputString);
  document.getElementById('stringResult').textContent = 'String without duplicates: ' + uniqueString;
}

function removeDuplicatesFromString(str) {
  return str
    .split('')
    .filter((char, index, self) => self.indexOf(char) === index)
    .join('');
}

In both examples, users can enter either a list of items (array) or a string in the input field, and the JavaScript code will remove duplicates and display the result.


Ques  8  InverteW right-angleW triangle pattern with asterisks


Ans  Creating an inverted right-angle triangle pattern with asterisks in JavaScript is a common exercise. Here's a simple example of how you can achieve this pattern:

// Define the number of rows for the triangle
const numRows = 5;

// Loop through each row
for (let i = 1; i <= numRows; i++) {
  // Create a string to store the asterisks for the current row
  let rowAsterisks = '';

  // Add asterisks to the row string
  for (let j = 1; j <= numRows - i; j++) {
    rowAsterisks += ' ';
  }
  for (let k = 1; k <= i; k++) {
    rowAsterisks += '*';
  }

  // Print the row
  console.log(rowAsterisks);
}


In this code, we define the number of rows for the inverted right-angle triangle using numRows. Then, we use nested loops to build the pattern row by row. The outer loop iterates through each row, and the inner loops add spaces and asterisks to the rowAsterisks string. Finally, we print the row to the console.

You can change the value of numRows to create triangles of different sizes.




Ques 9  Check for divisibility.


Ans  To check for divisibility of one number by another in JavaScript, you can use the modulo operator (%). The modulo operator returns the remainder when one number is divided by another. If the remainder is zero, it means the first number is divisible by the second number. Here's an example of how to check for divisibility:

// Define two numbers
const number1 = 15;
const number2 = 3;

// Check if number1 is divisible by number2
if (number1 % number2 === 0) {
  console.log(`${number1} is divisible by ${number2}`);
} else {
  console.log(`${number1} is not divisible by ${number2}`);
}

In this example, we check if number1 is divisible by number2 by calculating number1 % number2. If the result is zero, it means number1 is divisible by number2, and we print the message accordingly. If the result is not zero, it means number1 is not divisible by number2.

You can change the values of number1 and number2 to check for divisibility with different numbers.

Ques 10 Correct a bug

Ans To correct the bug where the quantity of each item in the cart is being recorded incorrectly by reducing it to half, you can write a JavaScript function that doubles the quantity of each item in the cart array. Here's an example of how you can do that:

// Sample cart array with item quantities (you should have your own cart data)
const cart = [
  { item: 'Product A', quantity: 2 },
  { item: 'Product B', quantity: 3 },
  { item: 'Product C', quantity: 4 },
];

// Function to correct the bug by doubling the item quantities
function correctCartBug(cart) {
  const correctedCart = cart.map(item => {
    // Double the quantity of each item
    return { ...item, quantity: item.quantity * 2 };
  });

  return correctedCart;
}

// Call the function to correct the cart
const correctedCart = correctCartBug(cart);

// Display the corrected cart
console.log('Corrected Cart:', correctedCart);

In this code, the correctCartBug function takes the cart array as input and uses the map method to create a new array with doubled item quantities. This corrected cart is then returned.

You should replace the sample cart array (cart) with your actual cart data. This function will fix the bug by doubling the item quantities in the cart.

Ques 11  Unit converter

Ans Creating a unit converter is a common task in programming. You can build a simple unit converter in JavaScript that converts units from one measurement system to another, such as converting meters to feet, or kilograms to pounds. Below is an example of a JavaScript program for a unit converter:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Unit Converter</title>
</head>
<body>
  <h1>Unit Converter</h1>
  <p>Enter a value:</p>
  <input type="number" id="inputValue">
  <p>Select a unit to convert from:</p>
  <select id="fromUnit">
    <option value="meters">Meters</option>
    <option value="kilograms">Kilograms</option>
  </select>
  <p>Select a unit to convert to:</p>
  <select id="toUnit">
    <option value="feet">Feet</option>
    <option value="pounds">Pounds</option>
  </select>
  <button onclick="convertUnits()">Convert</button>
  <p id="result"></p>
  <script src="script.js"></script>
</body>
</html>


JavaScript (script.js):

function convertUnits() {
  const inputValue = parseFloat(document.getElementById('inputValue').value);
  const fromUnit = document.getElementById('fromUnit').value;
  const toUnit = document.getElementById('toUnit').value;
  let result = 0;

  if (fromUnit === 'meters' && toUnit === 'feet') {
    result = inputValue * 3.28084;
  } else if (fromUnit === 'kilograms' && toUnit === 'pounds') {
    result = inputValue * 2.20462;
  }

  document.getElementById('result').textContent = `Result: ${inputValue} ${fromUnit} is ${result} ${toUnit}`;
}


In this example, users can enter a value, select the units to convert from and to, and click the "Convert" button. The JavaScript code handles the conversion based on the selected units and displays the result.

You can customize this code to include more unit conversions and units of measurement as needed for your specific unit converter.

Ques 12  Calculate rental cost


Ans  
To calculate the rental cost for a property, you need to consider various factors such as the daily or monthly rent, the number of days or months the property will be rented, and any additional fees. Here's a simple JavaScript program to calculate the rental cost based on these factors:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Rental Cost Calculator</title>
</head>
<body>
  <h1>Rental Cost Calculator</h1>
  <p>Enter the daily or monthly rent:</p>
  <input type="number" id="rentAmount">
  <p>Enter the number of days or months to rent:</p>
  <input type="number" id="rentDuration">
  <p>Enter any additional fees (optional):</p>
  <input type="number" id="additionalFees">
  <button onclick="calculateRentalCost()">Calculate</button>
  <p id="result"></p>
  <script src="script.js"></script>
</body>
</html>


JavaScript (script.js):

function calculateRentalCost() {
  const rentAmount = parseFloat(document.getElementById('rentAmount').value);
  const rentDuration = parseInt(document.getElementById('rentDuration').value);
  const additionalFees = parseFloat(document.getElementById('additionalFees').value);

  if (isNaN(rentAmount) || isNaN(rentDuration)) {
    document.getElementById('result').textContent = 'Please enter valid numbers for rent and duration.';
  } else {
    const rentalCost = (rentAmount * rentDuration) + (additionalFees || 0);
    document.getElementById('result').textContent = `Total Rental Cost: $${rentalCost}`;
  }
}


In this program, users can enter the daily or monthly rent, the number of days or months to rent, and any additional fees. When they click the "Calculate" button, the JavaScript code calculates the total rental cost, including the additional fees, and displays the result.

This is a basic example, and you can customize it to handle different rental scenarios and additional factors like discounts or taxes.

Ques 13 Bill splitter

Ans  
Creating a bill splitter in JavaScript is a useful tool for splitting a restaurant bill or other shared expenses among a group of people. Here's a simple example of a bill splitter program:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Bill Splitter</title>
</head>
<body>
  <h1>Bill Splitter</h1>
  <p>Enter the total bill amount:</p>
  <input type="number" id="totalBillAmount">
  <p>Enter the number of people:</p>
  <input type="number" id="numberOfPeople">
  <button onclick="splitBill()">Split Bill</button>
  <p id="result"></p>
  <script src="script.js"></script>
</body>
</html>

JavaScript (script.js):

function splitBill() {
  const totalBillAmount = parseFloat(document.getElementById('totalBillAmount').value);
  const numberOfPeople = parseInt(document.getElementById('numberOfPeople').value);

  if (isNaN(totalBillAmount) || isNaN(numberOfPeople) || numberOfPeople < 1) {
    document.getElementById('result').textContent = 'Please enter valid numbers for the bill and number of people.';
  } else {
    const individualShare = totalBillAmount / numberOfPeople;
    document.getElementById('result').textContent = `Each person owes: $${individualShare.toFixed(2)}`;
  }
}


In this program, users can enter the total bill amount and the number of people sharing the bill. When they click the "Split Bill" button, the JavaScript code calculates the individual share for each person and displays the result.

You can further customize this code to include options for splitting the bill, such as evenly or unevenly, or to include tip calculations and tax.


Ques 14  Calculate the final order price

Ans  
Calculating the final order price often involves factoring in various costs such as the item prices, quantities, tax, and any discounts. Here's a simple JavaScript program to calculate the final order price based on these factors:

HTML (index.html):


<!DOCTYPE html>
<html>
<head>
  <title>Final Order Price Calculator</title>
</head>
<body>
  <h1>Final Order Price Calculator</h1>
  <p>Enter the item price:</p>
  <input type="number" id="itemPrice">
  <p>Enter the quantity:</p>
  <input type="number" id="itemQuantity">
  <p>Enter the tax rate (in percentage):</p>
  <input type="number" id="taxRate">
  <p>Enter any discount (optional):</p>
  <input type="number" id="discountAmount">
  <button onclick="calculateFinalPrice()">Calculate</button>
  <p id="result"></p>
  <script src="script.js"></script>
</body>
</html>

JavaScript (script.js):

function calculateFinalPrice() {
  const itemPrice = parseFloat(document.getElementById('itemPrice').value);
  const itemQuantity = parseInt(document.getElementById('itemQuantity').value);
  const taxRate = parseFloat(document.getElementById('taxRate').value);
  const discountAmount = parseFloat(document.getElementById('discountAmount').value);

  if (isNaN(itemPrice) || isNaN(itemQuantity) || isNaN(taxRate)) {
    document.getElementById('result').textContent = 'Please enter valid numbers for item price, quantity, and tax rate.';
  } else {
    // Calculate the subtotal
    const subtotal = itemPrice * itemQuantity;

    // Calculate the tax amount
    const taxAmount = (taxRate / 100) * subtotal;

    // Apply the discount (if any)
    const discountedSubtotal = discountAmount ? subtotal - discountAmount : subtotal;

    // Calculate the final order price
    const finalPrice = discountedSubtotal + taxAmount;

    document.getElementById('result').textContent = `Final Order Price: $${finalPrice.toFixed(2)}`;
  }
}

In this program, users can enter the item price, quantity, tax rate (in percentage), and an optional discount amount. When they click the "Calculate" button, the JavaScript code calculates the final order price by factoring in the item price, quantity, tax, and discount, and then displays the result.

You can customize this code further to handle different pricing scenarios or additional factors like shipping costs or multiple items in the order.

Ques 15  Calculate the percentage of the discount 

Ans  To calculate the percentage of a discount, you need to know the original price and the discounted price. The formula to calculate the discount percentage is:

Discount Percentage
=
(
Original Price
−
Discounted Price
Original Price
)
×
100
Discount Percentage=( 
Original Price
Original Price−Discounted Price
​
 )×100

Here's a simple JavaScript program to calculate the discount percentage:

HTML (index.html):


<!DOCTYPE html>
<html>
<head>
  <title>Discount Percentage Calculator</title>
</head>
<body>
  <h1>Discount Percentage Calculator</h1>
  <p>Enter the original price:</p>
  <input type="number" id="originalPrice">
  <p>Enter the discounted price:</p>
  <input type="number" id="discountedPrice">
  <button onclick="calculateDiscountPercentage()">Calculate</button>
  <p id="result"></p>
  <script src="script.js"></script>
</body>
</html>


JavaScript (script.js):

function calculateDiscountPercentage() {
  const originalPrice = parseFloat(document.getElementById('originalPrice').value);
  const discountedPrice = parseFloat(document.getElementById('discountedPrice').value);

  if (isNaN(originalPrice) || isNaN(discountedPrice) || discountedPrice >= originalPrice) {
    document.getElementById('result').textContent = 'Please enter valid numbers for the original and discounted prices.';
  } else {
    const discountPercentage = ((originalPrice - discountedPrice) / originalPrice) * 100;
    document.getElementById('result').textContent = `Discount Percentage: ${discountPercentage.toFixed(2)}%`;
  }
}


In this program, users can enter the original price and the discounted price. When they click the "Calculate" button, the JavaScript code calculates the discount percentage using the formula and displays the result.

This code assumes that the discounted price is lower than the original price and that both values are valid numbers. You can further customize it to handle different scenarios or error checking.

Ques 16  Generate a random number

Ans  You can generate a random number in JavaScript using the Math.random() function. Here's an example:

// Generate a random number between 0 (inclusive) and 1 (exclusive)
const randomNumber = Math.random();

console.log(randomNumber);


This code will generate a random decimal number between 0 (inclusive) and 1 (exclusive). If you want to generate a random integer within a specific range, you can use the following code

function getRandomInt(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

// Generate a random integer between 1 and 100 (inclusive)
const randomInteger = getRandomInt(1, 100);

console.log(randomInteger);


In this example, the getRandomInt function generates a random integer between the min and max values (inclusive). You can customize the min and max values to set the range of random numbers you want.

Ques 17  Build a banking application

Ans  Building a complete banking application is a complex and multifaceted task that involves numerous security and compliance considerations. Such an application typically involves the development of user authentication, account management, transaction processing, and other financial services.

Below, I'll provide a simplified example of a basic banking application using HTML, CSS, and JavaScript for educational purposes. This example focuses on the user interface and simple operations, and it does not include actual security features that a real banking application would require.

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Simple Banking Application</title>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <h1>Simple Banking Application</h1>
  <div class="account">
    <h2>Your Account</h2>
    <p>Balance: $<span id="balance">1000</span></p>
    <input type="number" id="amount" placeholder="Enter amount">
    <button onclick="deposit()">Deposit</button>
    <button onclick="withdraw()">Withdraw</button>
  </div>
  <script src="script.js"></script>
</body>
</html>

CSS (styles.css):

body {
  font-family: Arial, sans-serif;
  text-align: center;
  background-color: #f0f0f0;
  margin: 0;
  padding: 0;
}

h1 {
  background-color: #333;
  color: white;
  padding: 10px;
}

.account {
  background-color: white;
  width: 300px;
  margin: 20px auto;
  padding: 10px;
  border: 1px solid #ccc;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
}

input {
  width: 100%;
  padding: 5px;
  margin: 5px 0;
}

button {
  width: 100%;
  padding: 5px;
  margin: 5px 0;
}

button:hover {
  background-color: #333;
  color: white;
  cursor: pointer;
}


JavaScript (script.js):

function deposit() {
  const amount = parseFloat(document.getElementById('amount').value);
  if (!isNaN(amount) && amount > 0) {
    const balanceElement = document.getElementById('balance');
    const currentBalance = parseFloat(balanceElement.textContent);
    balanceElement.textContent = (currentBalance + amount).toFixed(2);
  }
  document.getElementById('amount').value = '';
}

function withdraw() {
  const amount = parseFloat(document.getElementById('amount').value);
  const balanceElement = document.getElementById('balance');
  const currentBalance = parseFloat(balanceElement.textContent);
  
  if (!isNaN(amount) && amount > 0 && amount <= currentBalance) {
    balanceElement.textContent = (currentBalance - amount).toFixed(2);
  } else {
    alert('Invalid amount or insufficient balance.');
  }
  document.getElementById('amount').value = '';
}


In this simple example, users can deposit and withdraw funds from their account. The application starts with a balance of $1000, and users can input the amount they want to deposit or withdraw. The balance is updated accordingly, and basic validation checks are in place.

Please note that this is a highly simplified and non-secure example. In a real banking application, you would need to consider security, authentication, database storage, encryption, compliance with financial regulations, and much more.

Ques 18 Change Text on Button click.

Ans To change the text on a button click using JavaScript, you can create an HTML button element and use JavaScript to change its text when the button is clicked. Here's a simple example:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Change Text on Button Click</title>
</head>
<body>
  <h1>Change Text on Button Click</h1>
  <button id="myButton" onclick="changeText()">Click Me</button>
  <script src="script.js"></script>
</body>
</html>

JavaScript (script.js):

function changeText() {
  const button = document.getElementById('myButton');
  if (button.innerHTML === 'Click Me') {
    button.innerHTML = 'Text Changed!';
  } else {
    button.innerHTML = 'Click Me';
  }
}

In this example, we create a button element with the ID "myButton" and set its initial text to "Click Me." When the button is clicked, the changeText function is called. If the button's current text is "Click Me," it changes the text to "Text Changed!"; otherwise, it changes it back to "Click Me."

You can customize this code to change the button text to whatever you like when clicked.

Ques 19 Validate Password

Ans Password validation is an essential aspect of user authentication and security. You can use JavaScript to create a simple password validation function. Here's an example of how to check if a password meets specific criteria, such as a minimum length and the inclusion of certain character types (e.g., uppercase letters, lowercase letters, and numbers):

function validatePassword(password) {
  // Define the criteria
  const minLength = 8;
  const hasUppercase = /[A-Z]/.test(password);
  const hasLowercase = /[a-z]/.test(password);
  const hasDigit = /\d/.test(password);

  // Check if the password meets the criteria
  if (
    password.length >= minLength &&
    hasUppercase &&
    hasLowercase &&
    hasDigit
  ) {
    return true;
  } else {
    return false;
  }
}

// Example usage
const password = "MyPassword123";
const isValid = validatePassword(password);

if (isValid) {
  console.log("Password is valid.");
} else {
  console.log("Password is invalid. It must be at least 8 characters long and contain at least one uppercase letter, one lowercase letter, and one digit.");
}

n this code, the validatePassword function checks the password against the defined criteria. The criteria in this example include a minimum length of 8 characters, at least one uppercase letter, at least one lowercase letter, and at least one digit.

You can adjust the criteria or add additional requirements to fit your specific password validation needs. Additionally, you may want to consider more advanced password validation techniques for real-world applications, such as hashing and salting, to enhance security.

Ques  20  Dynamically Adding List Items to an Ordered List

Ans  To dynamically add list items to an ordered list (OL) using JavaScript, you can create a function that appends new list items (LI elements) to the existing ordered list. Here's an example:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Add List Items Dynamically</title>
</head>
<body>
  <h1>Add List Items Dynamically</h1>
  <input type="text" id="newItemText" placeholder="Enter a new item">
  <button onclick="addItemToList()">Add Item</button>
  <ol id="myList">
    <li>Item 1</li>
    <li>Item 2</li>
  </ol>
  <script src="script.js"></script>
</body>
</html>


JavaScript (script.js):

function addItemToList() {
  const newItemText = document.getElementById('newItemText').value;
  if (newItemText.trim() === '') {
    alert('Please enter a valid item.');
    return;
  }

  const myList = document.getElementById('myList');
  const newItem = document.createElement('li');
  newItem.textContent = newItemText;
  myList.appendChild(newItem);

  // Clear the input field after adding the item
  document.getElementById('newItemText').value = '';
}


In this example, users can enter a new item in the input field and click the "Add Item" button. The JavaScript function addItemToList retrieves the text from the input field, creates a new list item (<li>) element, sets its text to the entered value, and appends it to the existing ordered list (<ol>).

This code will add new items to the list dynamically. You can customize it further, for example, by allowing users to remove items or by adding more complex functionality based on your requirements.

Ques 21  TODO App

Ans  Creating a simple TODO app is a common project to learn web development. Here's a basic example of a TODO app using HTML, CSS, and JavaScript.

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>TODO App</title>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <h1>TODO App</h1>
  <div class="todo-container">
    <input type="text" id="todoInput" placeholder="Add a new task">
    <button onclick="addTodo()">Add</button>
    <ul id="todoList"></ul>
  </div>
  <script src="script.js"></script>
</body>
</html>


CSS (styles.css):

body {
  font-family: Arial, sans-serif;
  text-align: center;
  background-color: #f0f0f0;
  margin: 0;
  padding: 0;
}

h1 {
  background-color: #333;
  color: white;
  padding: 10px;
}

.todo-container {
  background-color: white;
  width: 300px;
  margin: 20px auto;
  padding: 10px;
  border: 1px solid #ccc;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
}

input[type="text"] {
  width: 80%;
  padding: 5px;
  margin: 5px 0;
}

button {
  width: 20%;
  padding: 5px;
  margin: 5px 0;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  background-color: #f0f0f0;
  padding: 5px;
  margin: 5px 0;
}

li button {
  background-color: #ff6347;
  color: white;
  border: none;
  padding: 3px 5px;
  margin-left: 5px;
  cursor: pointer;
}


JavaScript (script.js):

function addTodo() {
  const todoInput = document.getElementById('todoInput');
  const todoText = todoInput.value.trim();

  if (todoText === '') {
    alert('Please enter a task.');
    return;
  }

  const todoList = document.getElementById('todoList');
  const li = document.createElement('li');
  li.textContent = todoText;

  const deleteButton = document.createElement('button');
  deleteButton.textContent = 'Delete';
  deleteButton.onclick = function () {
    todoList.removeChild(li);
  };

  li.appendChild(deleteButton);
  todoList.appendChild(li);

  todoInput.value = '';
}


This example creates a basic TODO app where users can enter tasks, add them to the list, and delete them. Each task is displayed in an unordered list with a "Delete" button to remove it from the list. The app also includes minimal CSS styling for better presentation. You can further enhance the app by adding features like marking tasks as completed, filtering tasks, or persisting tasks in local storage.

Ques 22 Progress Bar

Ans Creating a progress bar in HTML, CSS, and JavaScript can be useful for displaying the progress of a task or process. Here's a basic example of a progress bar:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Progress Bar</title>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <h1>Progress Bar</h1>
  <div class="progress-container">
    <div class="progress-bar" id="myProgressBar"></div>
  </div>
  <button onclick="startProgress()">Start Progress</button>
  <script src="script.js"></script>
</body>
</html>


CSS (styles.css):

body {
  font-family: Arial, sans-serif;
  text-align: center;
  background-color: #f0f0f0;
  margin: 0;
  padding: 0;
}

h1 {
  background-color: #333;
  color: white;
  padding: 10px;
}

.progress-container {
  background-color: white;
  width: 300px;
  margin: 20px auto;
  padding: 10px;
  border: 1px solid #ccc;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
}

.progress-bar {
  background-color: #4CAF50;
  width: 0;
  height: 30px;
  text-align: center;
  line-height: 30px;
  color: white;
}

button {
  width: 100px;
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
  margin: 10px;
}


JavaScript (script.js):

function startProgress() {
  const progressBar = document.getElementById('myProgressBar');
  let width = 0;
  const interval = setInterval(frame, 10);

  function frame() {
    if (width >= 100) {
      clearInterval(interval);
    } else {
      width++;
      progressBar.style.width = width + '%';
      progressBar.textContent = width + '%';
    }
  }
}


In this example, there's a simple progress bar that starts at 0% and progresses to 100% when the "Start Progress" button is clicked. The startProgress function uses setInterval to increment the width of the progress bar over time.

You can customize this code to meet your specific needs, such as adjusting the progress duration or integrating it into a larger application.

Ques 23 Change the color on click

Ans  
To change the color of an element, such as text or a background, on a button click using JavaScript, you can create a function that toggles between colors. Here's a basic example of how to change the background color of an element on button click:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Change Color on Click</title>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <h1>Change Color on Click</h1>
  <div id="colorBox" class="color-box">
    Click the button to change my color!
  </div>
  <button onclick="changeColor()">Change Color</button>
  <script src="script.js"></script>
</body>
</html>


CSS (styles.css):

body {
  font-family: Arial, sans-serif;
  text-align: center;
  background-color: #f0f0f0;
  margin: 0;
  padding: 0;
}

h1 {
  background-color: #333;
  color: white;
  padding: 10px;
}

.color-box {
  background-color: #4CAF50;
  color: white;
  width: 300px;
  margin: 20px auto;
  padding: 20px;
  border: 1px solid #ccc;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
}

button {
  width: 150px;
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
  margin: 10px;
}

JavaScript (script.js):

function changeColor() {
  const colorBox = document.getElementById('colorBox');
  const currentColor = colorBox.style.backgroundColor;

  if (currentColor === 'rgb(76, 175, 80)') {
    colorBox.style.backgroundColor = 'rgb(244, 67, 54)';
  } else {
    colorBox.style.backgroundColor = 'rgb(76, 175, 80)';
  }
}


In this example, when the "Change Color" button is clicked, the changeColor function toggles the background color of the "colorBox" element between green and red.

You can adjust the colors and customize this code to change text color, border color, or any other CSS properties based on your requirements.

Ques 24 Text Highlighting

Ans  To highlight text dynamically using JavaScript, you can create a function that adds or removes CSS classes to the text element. Here's a basic example of how to highlight text on a button click:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Text Highlighting</title>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <h1>Text Highlighting</h1>
  <p id="highlightText">Click the button to highlight me!</p>body {
  font-family: Arial, sans-serif;
  text-align: center;
  background-color: #f0f0f0;
  margin: 0;
  padding: 0;
}

h1 {
  background-color: #333;
  color: white;
  padding: 10px;
}

#highlightText {
  background-color: transparent;
  color: #333;
  font-size: 20px;
  padding: 20px;
}

button {
  width: 150px;
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
  margin: 10px;
}


JavaScript (script.js):

function toggleHighlight() {
  const textElement = document.getElementById('highlightText');
  
  // Check if the element has the "highlighted" class
  if (textElement.classList.contains('highlighted')) {
    // If it does, remove the class to unhighlight the text
    textElement.classList.remove('highlighted');
  } else {
    // If it doesn't, add the class to highlight the text
    textElement.classList.add('highlighted');
  }
}

In this example, when the "Highlight Text" button is clicked, the toggleHighlight function toggles the "highlighted" class on the "highlightText" paragraph element. The CSS rules for the "highlighted" class define the background color, making the text appear highlighted.

You can customize this code to change the styling to suit your needs, such as changing the background color, text color, or other properties to create your desired highlighting effect.

Ques 25 Move the Image

Ans To move an image using JavaScript, you can change its position by modifying its CSS properties. Here's a basic example of how to move an image when a button is clicked:

HTML (index.html):

<!DOCTYPE html>
<html>
<head>
  <title>Move Image</title>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <h1>Move Image</h1>
  <div class="image-container">
    <img id="myImage" src="image.png" alt="Sample Image">
  </div>
  <button onclick="moveImage()">Move Image</button>
  <script src="script.js"></script>
</body>
</html>

CSS (styles.css):

body {
  font-family: Arial, sans-serif;
  text-align: center;
  background-color: #f0f0f0;
  margin: 0;
  padding: 0;
}

h1 {
  background-color: #333;
  color: white;
  padding: 10px;
}

.image-container {
  width: 300px;
  margin: 20px auto;
  border: 1px solid #ccc;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
  overflow: hidden;
}

#myImage {
  max-width: 100%;
  display: block;
  transition: transform 0.5s; /* Add transition for smooth movement */
}

button {
  width: 150px;
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
  margin: 10px;
}

JavaScript (script.js):

 function moveImage() {
  const myImage = document.getElementById('myImage');
  
  // Calculate the new position
  const currentPosition = myImage.style.transform || 'translateX(0)';
  const currentX = parseInt(currentPosition.match(/-?\d+/) || 0, 10); // Extract the current X position

  // Move the image to the right (add 50px)
  const newX = currentX + 50;
  myImage.style.transform = `translateX(${newX}px)`;
}


In this example, when the "Move Image" button is clicked, the moveImage function calculates the current X position of the image and moves it 50 pixels to the right by updating the transform property. A CSS transition is added for smooth movement.

You can adjust the amount by which the image is moved and add more complex movement logic as needed.


  <button onclick="toggleHighlight()">Highlight Text</button>
  <script src="script.js"></script>
</body>
</html>


CSS (styles.css):






