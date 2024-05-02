let budget = 0;
let expenses = [];

const budgetAmountInput = document.getElementById('budget-amount');
const setBudgetButton = document.getElementById('set-budget');
const expenseNameInput = document.getElementById('expense-name');
const expenseAmountInput = document.getElementById('expense-amount');
const addExpenseButton = document.getElementById('add-expense');
const budgetNumberSpan = document.getElementById('budget-number');
const expensesNumberSpan = document.getElementById('expenses-number');
const balanceNumberSpan = document.getElementById('balance-number');
const expenseList = document.querySelector('#expenses-list ul');
const resetButton = document.getElementById('reset-button');

setBudgetButton.addEventListener('click', function() {
  budget = parseFloat(budgetAmountInput.value);
  budgetNumberSpan.textContent = budget;
  calculateBalance();
});

addExpenseButton.addEventListener('click', function() {
  const expenseName = expenseNameInput.value;
  const expenseAmount = parseFloat(expenseAmountInput.value);

  if (expenseName && expenseAmount > 0) {
    expenses.push({ name: expenseName, amount: expenseAmount });
    updateExpenseList();
    expenseNameInput.value = '';
    expenseAmountInput.value = '';
    calculateBalance();
  }
});

resetButton.addEventListener('click', function() {
  budget = 0;
  expenses = [];
  budgetNumberSpan.textContent = budget;
  expensesNumberSpan.textContent = 0;
  balanceNumberSpan.textContent = 0;
  updateExpenseList();
});

function updateExpenseList() {
  expenseList.innerHTML = '';
  expenses.forEach(expense => {
    const listItem = document.createElement('li');
    listItem.textContent = `${expense.name}: $${expense.amount}`;
    expenseList.appendChild(listItem);
  });
}

function calculateBalance() {
  const totalExpenses = expenses.reduce((acc, expense) => acc + expense.amount, 0);
  expensesNumberSpan.textContent = totalExpenses;
  balanceNumberSpan.textContent = budget - totalExpenses;
}
