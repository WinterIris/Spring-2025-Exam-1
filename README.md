# Spring-2025-Exam-1

#include <iostream>
#include <iomanip>

using namespace std;

// Function to determine commission rate based on sales
double getCommissionRate(double sales) {
    if (sales < 10000) return 0.05;
    else if (sales < 15000) return 0.10;
    else if (sales < 18000) return 0.12;
    else if (sales < 22000) return 0.14;
    else return 0.16;
}

int main() {
    double sales, advancePay, commissionRate, commission, remainingPay;
    
    // Get user input
    cout << "Enter the salesperson's monthly sales: ";
    cin >> sales;
    cout << "Enter the amount of advanced pay for this salesperson: ";
    cin >> advancePay;
    
    // Determine commission rate
    commissionRate = getCommissionRate(sales);
    
    // Calculate commission
    commission = sales * commissionRate;
    
    // Calculate remaining pay after deducting advance
    remainingPay = commission - advancePay;
    
    // Display results
    cout << fixed << setprecision(2);
    cout << "\nPay Results\n";
    cout << "-----------\n";
    cout << "Sales: $" << sales << endl;
    cout << "Commission Rate: " << commissionRate << endl;
    cout << "Commission: $" << commission << endl;
    cout << "Advanced Pay: $" << advancePay << endl;
    cout << "Remaining Pay: $" << remainingPay << endl;
    
    // If remaining pay is negative, notify that the salesperson owes money
    if (remainingPay < 0) {
        cout << "The salesperson must reimburse Crazy Al's: $" << -remainingPay << endl;
    }
    
    return 0;
}
