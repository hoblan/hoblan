#include <iostream>
using namespace std;

int main() {
    int withdrawAmount;
    int password;
    
    cout << "ENTER YOUR PASSWORD: ";
    cin >> password;
    
    if (password == 0000) {  // Note: 0000 is treated as 0 in C++
        cout << "YOU HAVE 10,000 DOLLARS IN YOUR ACCOUNT\n";
    }
    else {
        cout << "WRONG PASSWORD. ACCESS DENIED.\n";
        return 0;
    }
    
    cout << "HOW MUCH DO YOU WANT TO WITHDRAW? ";
    cin >> withdrawAmount;
    
    if (withdrawAmount > 10000) {
        cout << "YOU DON'T HAVE ENOUGH MONEY\n";
    }
    else if (withdrawAmount < 5) {
        cout << "MINIMUM WITHDRAWAL IS $5\n";
    }
    else if (withdrawAmount % 5 != 0) {
        cout << "AMOUNT MUST BE IN MULTIPLES OF $5\n";
    }
    else {
        // Calculate how many bills of each denomination
        int fifties = withdrawAmount / 50;
        int remaining = withdrawAmount % 50;
        
        int twenties = remaining / 20;
        remaining = remaining % 20;
        
        int tens = remaining / 10;
        remaining = remaining % 10;
        
        int fives = remaining / 5;
        
        // Display results
        cout << "\nYOU WILL GET:\n";
        cout << fifties << " x $50 bill(s)\n";
        cout << twenties << " x $20 bill(s)\n";
        cout << tens << " x $10 bill(s)\n";
        cout << fives << " x $5 bill(s)\n";
        
        cout << "\nTOTAL WITHDRAWN: $" << withdrawAmount << endl;
    }

    return 0;
}
