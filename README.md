# nutrition-and-calorie-tracking-app
nutrition and calorie tracking app that calculates the amount of the total calorie, protein etc(nutrition), based on the food item that the user as selected 
<!DOCTYPE html>
<html>
<head>
<title>Nutrition Tracker</title>

<style>
body {
    font-family: Arial, sans-serif;
    background-color: #eef;
}

h1 {
    text-align: center;
    color: #2e7d32;
}

table {
    margin: auto;
    border-collapse: collapse;
    width: 70%;
}

th, td {
    border: 1px solid #333;
    padding: 10px;
    text-align: center;
}

th {
    background-color: #4caf50;
    color: white;
}

button {
    padding: 10px 20px;
    background-color: #2e7d32;
    color: white;
    border: none;
    cursor: pointer;
    font-size: 16px;
}

button:hover {
    background-color: #1b5e20;
}

.result {
    text-align: center;
    font-size: 18px;
    margin-top: 20px;
    font-weight: bold;
}
</style>

<script>
function calculateTotal() {
    let calories = 0;
    let protein = 0;

    const foods = document.querySelectorAll("input[type=checkbox]:checked");

    foods.forEach(food => {
        calories += parseFloat(food.dataset.cal);
        protein += parseFloat(food.dataset.protein);
    });

    document.getElementById("totalCalories").innerText = calories.toFixed(1);
    document.getElementById("totalProtein").innerText = protein.toFixed(1);
}
</script>

</head>

<body>

<h1>Nutrition & Calorie Tracking Website</h1>

<table>
<tr>
    <th>Select</th>
    <th>Food Item</th>
    <th>Calories (kcal)</th>
    <th>Protein (g)</th>
</tr>

<tr>
    <td><input type="checkbox" data-cal="130" data-protein="2.7"></td>
    <td>Rice</td>
    <td>130</td>
    <td>2.7</td>
</tr>

<tr>
    <td><input type="checkbox" data-cal="120" data-protein="3.0"></td>
    <td>Chapati</td>
    <td>120</td>
    <td>3.0</td>
</tr>

<tr>
    <td><input type="checkbox" data-cal="155" data-protein="13"></td>
    <td>Egg</td>
    <td>155</td>
    <td>13</td>
</tr>

<tr>
    <td><input type="checkbox" data-cal="42" data-protein="3.4"></td>
    <td>Milk</td>
    <td>42</td>
    <td>3.4</td>
</tr>

<tr>
    <td><input type="checkbox" data-cal="89" data-protein="1.1"></td>
    <td>Banana</td>
    <td>89</td>
    <td>1.1</td>
</tr>

</table>

<br>

<div style="text-align:center;">
    <button onclick="calculateTotal()">Calculate Total Nutrition</button>
</div>

<div class="result">
    Total Calories: <span id="totalCalories">0</span> kcal<br>
    Total Protein: <span id="totalProtein">0</span> g
</div>

<p style="text-align:center;">
Helps students and working professionals understand their daily nutritional intake.
</p>

</body>
</html>

