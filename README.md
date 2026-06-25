import java.util.Scanner;
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
    
