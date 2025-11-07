# Suman

#include <stdio.h>

int main() {
    int choice;
    float balance = 1000.0; // Let initial balance is 1000Rs
    float deposit, withdraw;

    printf("===== ATM SIMULATOR =====\n");

    while (1) {
        printf("\n-------- MENU --------\n");
        printf("1. Check Balance\n");
        printf("2. Deposit Money\n");
        printf("3. Withdraw Money\n");
        printf("4. Exit\n");
        printf("-----------------------\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        if (choice == 1) {
            printf("\nYour current balance: %.2fRs\n", balance);
        } 
        else if (choice == 2) {
            printf("Enter amount to deposit: Rs");
            scanf("%f", &deposit);
            if (deposit > 0) {
                balance += deposit;
                printf("%.2fRs deposited successfully!\n", deposit);
            } else {
                printf("Invalid amount!\n");
            }
        } 
        else if (choice == 3) {
            printf("Enter amount to withdraw: rs");
            scanf("%f", &withdraw);
            if (withdraw > 0 && withdraw <= balance) {
                balance -= withdraw;
                printf("%.2fRs withdrawn successfully!\n", withdraw);
            } else {
                printf("Insufficient balance or invalid amount!\n");
            }
        } 
        else if (choice == 4) {
            printf("\nThank you for using the ATM. Goodbye!\n");
            break;
        } 
        else {
            printf("Invalid choice! Please try again.\n");
        }
    }

    return 0;
}
