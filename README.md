<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Expense Tracker</title>
  <style>
    body { font-family: Arial; padding: 20px; background: #f5f5f5; }
    h2 { text-align: center; }
    .container { max-width: 400px; margin: auto; background: white; padding: 20px; border-radius: 8px; }
    input { width: 100%; padding: 8px; margin: 5px 0; }
    button { width: 100%; padding: 10px; background: green; color: white; border: none; cursor: pointer; }
    ul { list-style: none; padding: 0; }
    li { background: #eee; margin: 5px 0; padding: 10px; display: flex; justify-content: space-between; }
  </style>
</head>
<body>

<div class="container">
  <h2>Expense Tracker</h2>
  <input type="text" id="expenseName" placeholder="Expense Name">
  <input type="number" id="expenseAmount" placeholder="Amount">
  <button onclick="addExpense()">Add Expense</button>
  
  <h3>Expenses:</h3>
  <ul id="expenseList"></ul>
  <h3>Total: ₹<span id="totalExpense">0</span></h3>
</div>

<script>
  let total = 0;
  
  function addExpense() {
    const name = document.getElementById("expenseName").value;
    const amount = parseInt(document.getElementById("expenseAmount").value);
    
    if(name === "" || isNaN(amount)) {
      alert("Please enter valid details");
      return;
    }
    
    const li = document.createElement("li");
    li.textContent = `${name} - ₹${amount}`;
    document.getElementById("expenseList").appendChild(li);
    
    total += amount;
    document.getElementById("totalExpense").textContent = total;
    
    // Clear inputs
    document.getElementById("expenseName").value = "";
    document.getElementById("expenseAmount").value = "";
  }
</script>

</body>
</html>
