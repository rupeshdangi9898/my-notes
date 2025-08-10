<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Expense Tracker Notes</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .container {
            width: 100%;
            max-width: 1000px;
            background-color: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
            overflow: hidden;
        }
        
        header {
            background: linear-gradient(90deg, #4776E6 0%, #8E54E9 100%);
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
        }
        
        .logo {
            font-size: 2.5rem;
            margin-bottom: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
        }
        
        h1 {
            font-size: 2.2rem;
            margin-bottom: 5px;
        }
        
        .subtitle {
            font-size: 1.1rem;
            opacity: 0.9;
        }
        
        .dashboard {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            padding: 25px;
        }
        
        .card {
            background-color: white;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            padding: 25px;
            transition: transform 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-5px);
        }
        
        .card h2 {
            color: #4776E6;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.5rem;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #555;
        }
        
        input, textarea, select {
            width: 100%;
            padding: 14px;
            border: 2px solid #e1e5f0;
            border-radius: 10px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }
        
        input:focus, textarea:focus, select:focus {
            outline: none;
            border-color: #4776E6;
        }
        
        textarea {
            min-height: 120px;
            resize: vertical;
        }
        
        button {
            background: linear-gradient(90deg, #4776E6 0%, #8E54E9 100%);
            color: white;
            border: none;
            padding: 14px 25px;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1.1rem;
            font-weight: 600;
            width: 100%;
            transition: all 0.3s ease;
            box-shadow: 0 4px 10px rgba(71, 118, 230, 0.3);
        }
        
        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(71, 118, 230, 0.4);
        }
        
        .expense-form {
            background: linear-gradient(135deg, #fdfcfb 0%, #e2d1c3 100%);
        }
        
        .expense-form h2 {
            color: #e44d26;
        }
        
        .expense-form button {
            background: linear-gradient(90deg, #e44d26 0%, #f16529 100%);
            box-shadow: 0 4px 10px rgba(228, 77, 38, 0.3);
        }
        
        .expense-form button:hover {
            box-shadow: 0 6px 15px rgba(228, 77, 38, 0.4);
        }
        
        .display-area {
            grid-column: span 2;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        }
        
        .tabs {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 2px solid #e1e5f0;
        }
        
        .tab {
            padding: 12px 25px;
            cursor: pointer;
            font-weight: 600;
            color: #666;
            transition: all 0.3s ease;
        }
        
        .tab.active {
            color: #4776E6;
            border-bottom: 3px solid #4776E6;
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        .list {
            max-height: 300px;
            overflow-y: auto;
            padding-right: 10px;
        }
        
        .list-item {
            background: white;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 15px;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.05);
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            position: relative;
        }
        
        .note-content {
            flex: 1;
        }
        
        .note-title {
            font-weight: 700;
            margin-bottom: 8px;
            color: #333;
        }
        
        .note-text {
            color: #666;
            line-height: 1.5;
        }
        
        .expense-item {
            display: flex;
            justify-content: space-between;
            width: 100%;
        }
        
        .expense-details {
            flex: 1;
        }
        
        .expense-amount {
            font-weight: 700;
            color: #e44d26;
            font-size: 1.2rem;
        }
        
        .expense-category {
            display: inline-block;
            background: #e1e5f0;
            padding: 3px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            margin-top: 5px;
        }
        
        .item-date {
            color: #999;
            font-size: 0.85rem;
            margin-top: 8px;
        }
        
        .delete-btn {
            background: #ff6b6b;
            color: white;
            border: none;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: background 0.3s;
        }
        
        .delete-btn:hover {
            background: #ff5252;
        }
        
        .total-display {
            background: white;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            margin-top: 20px;
        }
        
        .total-label {
            font-size: 1.2rem;
            color: #666;
            margin-bottom: 10px;
        }
        
        .total-amount {
            font-size: 2.5rem;
            font-weight: 700;
            color: #e44d26;
        }
        
        .empty-state {
            text-align: center;
            padding: 40px 0;
            color: #999;
        }
        
        .empty-state i {
            font-size: 3rem;
            margin-bottom: 15px;
            opacity: 0.5;
        }
        
        @media (max-width: 768px) {
            .dashboard {
                grid-template-columns: 1fr;
            }
            
            .display-area {
                grid-column: span 1;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <i class="fas fa-file-invoice-dollar"></i>
                <h1>Expense Tracker Notes</h1>
            </div>
            <p class="subtitle">Track your notes and expenses in one place</p>
        </header>
        
        <div class="dashboard">
            <div class="card">
                <h2><i class="fas fa-sticky-note"></i> Create Note</h2>
                <div class="form-group">
                    <label for="noteTitle">Title</label>
                    <input type="text" id="noteTitle" placeholder="Note title...">
                </div>
                <div class="form-group">
                    <label for="noteContent">Content</label>
                    <textarea id="noteContent" placeholder="Write your note here..."></textarea>
                </div>
                <button id="addNoteBtn"><i class="fas fa-plus"></i> Add Note</button>
            </div>
            
            <div class="card expense-form">
                <h2><i class="fas fa-receipt"></i> Add Expense</h2>
                <div class="form-group">
                    <label for="expenseName">Description</label>
                    <input type="text" id="expenseName" placeholder="What did you spend on?">
                </div>
                <div class="form-group">
                    <label for="expenseAmount">Amount (₹)</label>
                    <input type="number" id="expenseAmount" placeholder="Enter amount" min="0" step="0.01">
                </div>
                <div class="form-group">
                    <label for="expenseCategory">Category</label>
                    <select id="expenseCategory">
                        <option value="food">Food & Dining</option>
                        <option value="shopping">Shopping</option>
                        <option value="transport">Transportation</option>
                        <option value="entertainment">Entertainment</option>
                        <option value="utilities">Utilities</option>
                        <option value="health">Health & Fitness</option>
                        <option value="other">Other</option>
                    </select>
                </div>
                <button id="addExpenseBtn"><i class="fas fa-plus"></i> Add Expense</button>
            </div>
            
            <div class="card display-area">
                <div class="tabs">
                    <div class="tab active" data-tab="notes">Notes</div>
                    <div class="tab" data-tab="expenses">Expenses</div>
                    <div class="tab" data-tab="summary">Summary</div>
                </div>
                
                <div class="tab-content active" id="notes-content">
                    <h3>Your Notes</h3>
                    <div class="list" id="notes-list">
                        <div class="empty-state">
                            <i class="fas fa-sticky-note"></i>
                            <p>No notes yet. Add your first note!</p>
                        </div>
                    </div>
                </div>
                
                <div class="tab-content" id="expenses-content">
                    <h3>Expense History</h3>
                    <div class="list" id="expenses-list">
                        <div class="empty-state">
                            <i class="fas fa-receipt"></i>
                            <p>No expenses recorded yet. Add your first expense!</p>
                        </div>
                    </div>
                </div>
                
                <div class="tab-content" id="summary-content">
                    <h3>Financial Summary</h3>
                    <div class="total-display">
                        <div class="total-label">Total Expenses</div>
                        <div class="total-amount">₹<span id="totalAmount">0.00</span></div>
                    </div>
                    <div id="expense-chart" style="height: 200px; margin-top: 20px; display: flex; align-items: flex-end; justify-content: space-around; padding: 0 20px;">
                        <!-- Chart bars will be generated by JS -->
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <script>
        // Data storage
        let notes = JSON.parse(localStorage.getItem('notes')) || [];
        let expenses = JSON.parse(localStorage.getItem('expenses')) || [];
        
        // DOM elements
        const notesList = document.getElementById('notes-list');
        const expensesList = document.getElementById('expenses-list');
        const totalAmountDisplay = document.getElementById('totalAmount');
        const expenseChart = document.getElementById('expense-chart');
        
        // Initialize the app
        document.addEventListener('DOMContentLoaded', () => {
            renderNotes();
            renderExpenses();
            updateTotal();
            renderChart();
            
            // Setup tab switching
            document.querySelectorAll('.tab').forEach(tab => {
                tab.addEventListener('click', () => {
                    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
                    document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
                    
                    tab.classList.add('active');
                    document.getElementById(`${tab.dataset.tab}-content`).classList.add('active');
                });
            });
            
            // Add note button
            document.getElementById('addNoteBtn').addEventListener('click', addNote);
            
            // Add expense button
            document.getElementById('addExpenseBtn').addEventListener('click', addExpense);
        });
        
        // Add a new note
        function addNote() {
            const title = document.getElementById('noteTitle').value.trim();
            const content = document.getElementById('noteContent').value.trim();
            
            if (!title || !content) {
                alert('Please enter both title and content for your note.');
                return;
            }
            
            const newNote = {
                id: Date.now(),
                title,
                content,
                date: new Date().toLocaleString()
            };
            
            notes.push(newNote);
            saveToLocalStorage();
            renderNotes();
            
            // Clear form
            document.getElementById('noteTitle').value = '';
            document.getElementById('noteContent').value = '';
        }
        
        // Add a new expense
        function addExpense() {
            const name = document.getElementById('expenseName').value.trim();
            const amount = parseFloat(document.getElementById('expenseAmount').value);
            const category = document.getElementById('expenseCategory').value;
            
            if (!name || isNaN(amount) || amount <= 0) {
                alert('Please enter a valid description and amount for your expense.');
                return;
            }
            
            const newExpense = {
                id: Date.now(),
                name,
                amount,
                category,
                date: new Date().toLocaleString()
            };
            
            expenses.push(newExpense);
            saveToLocalStorage();
            renderExpenses();
            updateTotal();
            renderChart();
            
            // Clear form
            document.getElementById('expenseName').value = '';
            document.getElementById('expenseAmount').value = '';
        }
        
        // Delete a note
        function deleteNote(id) {
            notes = notes.filter(note => note.id !== id);
            saveToLocalStorage();
            renderNotes();
        }
        
        // Delete an expense
        function deleteExpense(id) {
            expenses = expenses.filter(expense => expense.id !== id);
            saveToLocalStorage();
            renderExpenses();
            updateTotal();
            renderChart();
        }
        
        // Render all notes
        function renderNotes() {
            if (notes.length === 0) {
                notesList.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-sticky-note"></i>
                        <p>No notes yet. Add your first note!</p>
                    </div>
                `;
                return;
            }
            
            notesList.innerHTML = '';
            notes.forEach(note => {
                const noteElement = document.createElement('div');
                noteElement.className = 'list-item';
                noteElement.innerHTML = `
                    <div class="note-content">
                        <div class="note-title">${note.title}</div>
                        <div class="note-text">${note.content}</div>
                        <div class="item-date">${note.date}</div>
                    </div>
                    <button class="delete-btn" onclick="deleteNote(${note.id})">
                        <i class="fas fa-trash"></i>
                    </button>
                `;
                notesList.appendChild(noteElement);
            });
        }
        
        // Render all expenses
        function renderExpenses() {
            if (expenses.length === 0) {
                expensesList.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-receipt"></i>
                        <p>No expenses recorded yet. Add your first expense!</p>
                    </div>
                `;
                return;
            }
            
            expensesList.innerHTML = '';
            expenses.forEach(expense => {
                const expenseElement = document.createElement('div');
                expenseElement.className = 'list-item';
                
                // Get category icon
                let categoryIcon = 'fas fa-question';
                switch(expense.category) {
                    case 'food': categoryIcon = 'fas fa-utensils'; break;
                    case 'shopping': categoryIcon = 'fas fa-shopping-cart'; break;
                    case 'transport': categoryIcon = 'fas fa-bus'; break;
                    case 'entertainment': categoryIcon = 'fas fa-film'; break;
                    case 'utilities': categoryIcon = 'fas fa-lightbulb'; break;
                    case 'health': categoryIcon = 'fas fa-heartbeat'; break;
                    default: categoryIcon = 'fas fa-question';
                }
                
                expenseElement.innerHTML = `
                    <div class="expense-item">
                        <div class="expense-details">
                            <div class="note-title">${expense.name}</div>
                            <div class="expense-amount">₹${expense.amount.toFixed(2)}</div>
                            <div class="expense-category"><i class="${categoryIcon}"></i> ${expense.category.charAt(0).toUpperCase() + expense.category.slice(1)}</div>
                        </div>
                        <div>
                            <div class="item-date">${expense.date}</div>
                        </div>
                    </div>
                    <button class="delete-btn" onclick="deleteExpense(${expense.id})">
                        <i class="fas fa-trash"></i>
                    </button>
                `;
                expensesList.appendChild(expenseElement);
            });
        }
        
        // Calculate and display total expenses
        function updateTotal() {
            const total = expenses.reduce((sum, expense) => sum + expense.amount, 0);
            totalAmountDisplay.textContent = total.toFixed(2);
        }
        
        // Render chart for expense categories
        function renderChart() {
            // Group expenses by category
            const categories = {
                food: 0,
                shopping: 0,
                transport: 0,
                entertainment: 0,
                utilities: 0,
                health: 0,
                other: 0
            };
            
            expenses.forEach(expense => {
                categories[expense.category] += expense.amount;
            });
            
            // Find max value for scaling
            const maxValue = Math.max(...Object.values(categories), 1);
            
            // Generate chart bars
            expenseChart.innerHTML = '';
            for (const [category, amount] of Object.entries(categories)) {
                if (amount > 0) {
                    const barHeight = (amount / maxValue) * 150;
                    const bar = document.createElement('div');
                    bar.style.cssText = `
                        width: 40px;
                        height: ${barHeight}px;
                        background: linear-gradient(to top, #e44d26, #f16529);
                        border-radius: 5px 5px 0 0;
                        display: flex;
                        flex-direction: column;
                        justify-content: flex-end;
                        align-items: center;
                        margin: 0 5px;
                    `;
                    
                    // Add label
                    const label = document.createElement('div');
                    label.textContent = category.charAt(0).toUpperCase();
                    label.style.cssText = `
                        color: white;
                        font-weight: bold;
                        padding: 5px 0;
                    `;
                    bar.appendChild(label);
                    
                    // Add tooltip
                    bar.title = `${category.charAt(0).toUpperCase() + category.slice(1)}: ₹${amount.toFixed(2)}`;
                    
                    expenseChart.appendChild(bar);
                }
            }
        }
        
        // Save data to localStorage
        function saveToLocalStorage() {
            localStorage.setItem('notes', JSON.stringify(notes));
            localStorage.setItem('expenses', JSON.stringify(expenses));
        }
    </script>
</body>
</html>
