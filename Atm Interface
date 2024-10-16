package org.atm;
import java.util.Scanner;

public class BankAccount {

    private double balance;

    public BankAccount(double balance) {
        this.balance = balance;
    }

    public double getBalance() {
        return balance;
    }

    public boolean deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            return true;
        } else {
            System.out.println("Invalid Amount.");
            return false;
        }
    }

    public boolean withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            return true;
        } else {
            System.out.println("Invalid withdrawal amount or insufficient balance.");
            return false;
        }
    }

    public static class ATM {
        private BankAccount userAccount;

        public ATM(BankAccount userAccount) {
            this.userAccount = userAccount;
        }

        public void displayOptions() {
            System.out.println("1. Cash Withdraw");
            System.out.println("2. Cash Deposit");
            System.out.println("3. Balance Enquiry");
            System.out.println("4. Exit");
        }

        public void withdraw() {
            Scanner scanner = new Scanner(System.in);
            System.out.print("Enter the amount to withdraw: ");
            double amount = scanner.nextDouble();

            if (userAccount.withdraw(amount)) {
                System.out.println("Withdrawal successful. Remaining balance: " + userAccount.getBalance());
            }
        }

        public void deposit() {
            Scanner scanner = new Scanner(System.in);
            System.out.print("Enter the deposit amount: ");
            double amount = scanner.nextDouble();

            if (userAccount.deposit(amount)) {
                System.out.println("Deposit successful. New balance: " + userAccount.getBalance());
            }
        }

        public void checkBalance() {
            System.out.println("Your balance is: " + userAccount.getBalance());
        }

        public void start() {
            Scanner scanner = new Scanner(System.in);

            while (true) {
                displayOptions();
                System.out.print("Enter your choice 1-4: ");
                int choice = scanner.nextInt();

                switch (choice) {
                    case 1:
                        withdraw();
                        break;
                    case 2:
                        deposit();
                        break;
                    case 3:
                        checkBalance();
                        break;
                    case 4:
                        System.out.println("Exiting. Thank you!");
                        scanner.close();
                        return;
                    default:
                        System.out.println("Invalid choice. Please try again.");
                }
            }
        }
    }

    public static class AtmMachine {
        public static void main(String[] args) {
            BankAccount userAccount = new BankAccount(100000);
            ATM atmMachine = new ATM(userAccount);
            atmMachine.start();
        }
    }
}
