# ATM Interface - CodSoft Task 3

## 📌 Description

This project is a simple console-based **ATM Interface** developed in Java as part of the **CodSoft Java Programming Internship**. The application simulates basic ATM operations such as checking account balance, depositing money, and withdrawing money.

## ✨ Features

* Check Account Balance
* Deposit Money
* Withdraw Money
* Validate User Input
* Display Appropriate Messages
* Exit the Application

## 🛠️ Technologies Used

* Java
* Object-Oriented Programming (OOP)
* Scanner Class

## 📂 Project Structure

* **Bank Class** - Manages account balance, deposits, and withdrawals.
* **AutomatedTellerMachine Class** - Provides the ATM menu and user interaction.
* **Main Class** - Executes the ATM application.

##  Program

mport java.util.Scanner;
class Bank{
private double bal;
    public Bank(double initialbal){
    bal= initialbal;
    }
    public double getbal(){
      return bal;
    }
    public void deposit(double amt){
      bal+=amt;
      System.out.println("Amount deposited successfully!");
    }
    public boolean withdraw(double amt){
      if(amt<=bal){
        bal-=amt;
        return true;
      }
      return false;
    }
    }
    class AutomatedTellerMachine{
      private Bank account;
      public AutomatedTellerMachine(Bank account){
        this.account=account;
      }
      public void menu(){
        Scanner sc=new Scanner(System.in);
        int option;
        do{
          System.out.println("\n====AutomatedTellerMachine");
          System.out.println("1.Check balance");
          System.out.println("2.Cash deposit");
          System.out.println("3.cash withdrawl");
          System.out.println("4.Exit");
          System.out.print("Enter your option");
          option=sc.nextInt();
          switch(option){
            case 1:
            System.out.println("current bal:Rs." + account.getbal());
            break;
            case 2:
            System.out.print("Enter cash to deposit: ");
            double cashdeposit=sc.nextDouble();
            if(cashdeposit>0){
              account.deposit(cashdeposit);
            }else{
              System.out.println("Invalid Amount!");
            }
            break;
            case 3:
            System.out.println("Enter cash to withdraw: ");
            double cashwithdraw=sc.nextDouble();
            if(cashwithdraw>0){
              if(account.withdraw(cashwithdraw)){
                System.out.println("withdrawl successfull!");
              }else{
                System.out.println("Insufficient balance!");
              }
              }else{
                System.out.println("Invalid Amount!");
              }
              break;
              case 4:
              System.out.println("Thankyou so much for using ATM!");
              break;
              default:
              System.out.println("Invalid option!");
            }
          }while(option!=4);
        }
      }
      public class Main{
        public static void main(String[]args){
          Bank account=new Bank(5000);
          AutomatedTellerMachine atm=new AutomatedTellerMachine(account);
          atm.menu();
        }
      }

## ▶️ How to Run

1. Clone this repository.
2. Open the project in any Java IDE (Eclipse, IntelliJ IDEA, VS Code, etc.).
3. Compile and run the `Main.java` file.
4. Follow the on-screen instructions to perform ATM operations.

## 💻 Sample Operations

* Check Balance
* Deposit Cash
* Withdraw Cash
* Exit ATM

## Sample output


====AutomatedTellerMachine
1.Check balance
2.Cash deposit
3.cash withdrawl
4.Exit
Enter your option1
current bal:Rs.5000.0

====AutomatedTellerMachine
1.Check balance
2.Cash deposit
3.cash withdrawl
4.Exit
Enter your option2
Enter cash to deposit: 45000
Amount deposited successfully!

====AutomatedTellerMachine
1.Check balance
2.Cash deposit
3.cash withdrawl
4.Exit
Enter your option3
Enter cash to withdraw: 
5000
withdrawl successfull!

====AutomatedTellerMachine
1.Check balance
2.Cash deposit
3.cash withdrawl
4.Exit
Enter your option1
current bal:Rs.45000.0

====AutomatedTellerMachine
1.Check balance
2.Cash deposit
3.cash withdrawl
4.Exit
Enter your option4
Thankyou so much for using ATM!
Ready

Terminal


## 🎯 Internship

This project was developed as **Task 3** for the **CodSoft Java Programming Internship**.

## 👩‍💻 Author

**Sharmila M**
