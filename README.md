#ExpenseTracker
This project is a command-line and Jupyter Notebook-based Expense Tracker built using Python, Pandas, NumPy and Matplotlib.

#The application simulates a simple finance tool that:
- Loads expenses from a CSV file
- Displays total spending overview
- Performs category-wise analysis (sum, count, percentage)
- Allows users to filter expenses by date range
- Generates pie chart visualizations for expenses
- Allows the user to input data to the existing data/table
- Exports a summary report to `summary_report.csv`

All logic is implemented with basic Python.

#How to Run It
Using the Jupyter Notebook
 
1. Open `Expenses_Tracker.ipynb` in any Jupyter environment (e.g., VS Code, Jupyter Lab, Google Colab)
2. Ensure `expenses.csv` is in the same folder
3. Run each cell in order

#Install essential Library required:
pandas for imoorting data
numpy for calculation
matplotlib for creating charts,plots etc..

eg.pip install pandas numpy matplotlib!

#sample output:
- Loads expenses from a CSV file
data = pd.read_csv("expenses.csv")
data.head()
output:
Date	Category	Amount	Description
0	10-06-2025	Food	150	Pizza at Dominos
1	11-06-2025	Transport	50	Rickshaw fare
2	12-06-2025	Rent	5000	June Rent
3	12-06-2025	Utilities	200	Electricity Bill

- Displays total spending overview
def total_spending_overview(data):
    # Total spent
    total_spent = data['Amount'].sum()
    print(f"\nTotal Amount Spent: ₹{total_spent}")
total_spending_summary=total_spending_overview(data)
print(total_spending_summary)

output:
Total Amount Spent: ₹5400

- Generates pie chart visualizations for expenses
def plot_expense_pie_chart(data):
    # Group by category and sum the amounts
    category_sums = data.groupby("Category")["Amount"].sum()
    # Define color palette (optional: pick any)
    colors = plt.cm.Paired(range(len(category_sums)))
    # Plot pie chart
    plt.figure(figsize=(6,6))
    wedges, texts, autotexts = plt.pie(
        category_sums,
        labels=category_sums.index,     # This shows the category names on the chart
        autopct='%1.1f%%',
        colors=colors,
        startangle=140
    )
    # Title
    plt.title("Expense Breakdown by Category")
    # Legend (to show color-code if labels overlap)
    plt.legend(wedges, category_sums.index, title="Categories", loc="center left", bbox_to_anchor=(1, 0, 0.5, 1))
    # Make it a perfect circle
    plt.axis('equal')
    # Show chart
    plt.tight_layout()
    plt.show()

output:
![download](https://github.com/user-attachments/assets/1c886f8b-2f38-4a94-98b0-244152a277f8)

#Features Implemented
 Total Spending Overview (Total, Highest, Lowest)
 Category-wise Summary (Sum, Count, Percentage)
 Pie Chart Visualization using Matplotlib 
 Filter expenses by custom date range
 Add new expense via user input and update CSV
 Export summary to summary_report.csv
 


A simple and interactive expense tracker using Python, Pandas, and NumPy.





 
