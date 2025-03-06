#include <iostream>
using namespace std;


class bankSystem {
	private:
	string accountName;
	int accountPin;
	int accountBalance;
	string accountType;
	
	public:
	void setUser1 (string accountName, int accountPin, int accountBalance, string accountType){
	this -> accountName = accountName;
	this -> accountPin = accountPin;
	this -> accountBalance = accountBalance;
	this -> accountType = accountType;
	}
	
	void depositOr(string choice, int amount){
		
		if (choice == "Deposit" || choice == "deposit"){
				
	   if (amount > 0){
	   
		this ->	accountBalance = accountBalance + amount;
	}
		else {
		this ->	accountBalance = accountBalance;
		}
	}
	
	  else if (choice == "Withdraw" || choice == "withdraw"){
	  	
	  	if (amount > 0){
			this -> accountBalance = accountBalance - amount;
		}
		else {
		this ->	accountBalance = accountBalance;
		}
	}
}
	
	void getUser1 (){
		cout << "Username:" << accountName << endl;
		cout << "accout PIN: " << accountPin << endl;
		cout << "Account Balance: " << accountBalance << endl;
		cout << "Account Type: " << accountType << endl;
	}
	
};


int main (){
	string name;
	int pin, amount;
	string type, choice;
	int balance = 0;
	
	bankSystem bank;
	
	cout << "enter your name: ";
	cin >> name;
	cout << "enter your pin: ";
	cin >> pin;
	cout << "enter your balance: ";
	cin >> balance;
	cout << "enter the account type: ";
	cin >> type;

	bank.setUser1 (name,pin,balance,type);
	
   cout << "do you want to deposit or withdraw:" << endl;
   cin >> choice;
   
   if (choice == "Deposit" || choice == "deposit" || choice == "DEPOSIT"){
   	cout << "enter the amount you want to deposit: ";
   	cin >> amount;
    bank.depositOr(choice,amount);
   	bank.getUser1();  
 }
 
  else if (choice == "Withdraw" || choice == "withdraw"){
  	cout << "enter the amount you want to withdraw: ";
  	cin >> amount;
  	bank.depositOr(choice,amount);
  	bank.getUser1();  
  }

	return 0;
}
