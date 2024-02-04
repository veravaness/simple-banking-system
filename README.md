class BankAccount {
  String accountHolder;
  double balance;

  BankAccount(this.accountHolder, this.balance);

  void deposit(double amount) {
    if (amount > 0) {
      balance += amount;
      print('Deposit successful. New balance: \$${balance.toStringAsFixed(2)}');
    } else {
      print('Invalid deposit amount.');
    }
  }

  void withdraw(double amount) {
    if (amount > 0 && amount <= balance) {
      balance -= amount;
      print('Withdrawal successful. New balance: \$${balance.toStringAsFixed(2)}');
    } else {
      print('Invalid withdrawal amount or insufficient funds.');
    }
  }

  double checkBalance() {
    return balance;
  }
}

void main() {
  BankAccount myAccount = BankAccount('John Doe', 1000.0);

  print('Initial balance: \$${myAccount.checkBalance().toStringAsFixed(2)}');

  myAccount.deposit(500.0);
  myAccount.withdraw(200.0);
  myAccount.withdraw(800.0); // This should fail due to insufficient funds

  print('Final balance: \$${myAccount.checkBalance().toStringAsFixed(2)}');
}
