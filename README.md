# LEGOIO-Python-project
Create a class BankAccount with the following features:
A constructor that initializes the account holder's name and intial balance (default is 0)
A method deposit(amount) to add money to the account'
a method withdraw(amount) that substracts money from the account only if sufficient funds exist otherwise prints "Insufficient balance"
a method display_balance() to show the current balance
then create a subclass SavingAccount that adds:
An attribute interest_rate (e.g., 0.05 for 5%)
A method add_interest() that calculates and adds interest to the balance

Tasks:
1. Create a SavingsAccount object for a user name "Alice" with an initial balance of 10,000 and an interst rate of 5%
2. Deposit 2,000, withdraw 3,000, and add interest.
3. Display the final balance
class Account:
    def __init__(self, name, balance=0):
        self.name = name
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount
        print(f"Deposited {amount}. New balance: {self.balance}")

    def withdraw(self, amount):
        if self.balance >= amount:
            self.balance -= amount
            print(f"Withdrew {amount}. New balance: {self.balance}")
        else:
            print("Insufficient balance")

    def display_balance(self):
        print(f"{self.name}'s current balance: {self.balance}")


class SavingsAccount(Account):
    def __init__(self, name, balance=0, interest_rate=0.05):
        super().__init__(name, balance)
        self.interest_rate = interest_rate

    def add_interest(self):
        interest = self.balance * self.interest_rate
        self.balance += interest
        print(f"Interest added: {interest}. New balance: {self.balance}")


# --- Tasks ---
# 1. Create account for Alice
alice_account = SavingsAccount("Alice", 10000, 0.05)

# 2. Deposit 2000, withdraw 3000, and add interest
alice_account.deposit(2000)
alice_account.withdraw(3000)
alice_account.add_interest()

# 3. Display final balance
alice_account.display_balance()
