import datetime

class ExpenseTracker:
    expenses = []
    def init(self):
        """Initialize the expense tracker with an empty list."""
        self.expenses = []

    def add_expense(self, category, amount, description):
        """
        Add an expense to the tracker.

        Parameters:
        category (str): The category of the expense.
        amount (float): The amount of the expense.
        description (str): The description of the expense.

        Raises:
        ValueError: If the amount is not a positive number.
        """
        try:
            if amount <= 0:
                raise ValueError("Amount must be a positive number.")
            expense = {
                'category': category,
                'amount': amount,
                'description': description,
                'date': datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
            }
            self.expenses.append(expense)
            print("Expense added successfully.")
        except ValueError as ve:
            print(f"Error: {ve}")
        except Exception as e:
            print(f"An unexpected error occurred: {e}")

    def view_expenses(self):
        """Print all the expenses in the tracker."""
        if not self.expenses:
            print("No expenses found.")
            return

        for i, expense in enumerate(self.expenses, start=1):
            print(f"{i}. Date: {expense['date']},Category: {expense['category']}, Amount: {expense['amount']}, Description: {expense['description']}")

    def delete_expense(self, index):
        """
        Delete an expense from the tracker.

        Parameters:
        index (int): The index of the expense to delete.

        Raises:
        IndexError: If the index is out of range.
        """
        try:
            if index < 1 or index > len(self.expenses):
                raise IndexError("Invalid index. Please enter a valid expense number.")
            del self.expenses[index - 1]
            print("Expense deleted successfully.")
        except IndexError as ie:
            print(f"Error: {ie}")
        except Exception as e:
            print(f"An unexpected error occurred: {e}")


tracker = ExpenseTracker()  
while True:
    print("\nExpense Tracker")
    print("1. Add Expense")
    print("2. View Expenses")
    print("3. Exit")
    choice = input("Enter your choice: ")

    if choice == '1':
        try:
            category = input("Enter the category: ")
            amount = float(input("Enter the amount: "))
            description = input("Enter the description: ")
            tracker.add_expense(category,amount, description)
        except ValueError:
            print("Invalid input. Please enter a valid amount.")
        except Exception as e:
            print(f"An unexpected error occurred: {e}")
    elif choice == '2':
        tracker.view_expenses()
    elif choice == '3':
        print("Exiting the tracker.")
        break
    else:
        print("Invalid choice. Please try again.")

if _name_ == "main":
    tracker = ExpenseTracker()
