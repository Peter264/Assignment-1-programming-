# Assignment-1-programming-
#include <stdio.h>

int main() {
    int bookID, dueDate, returnDate, daysOverdue = 0;
    int fine = 0;
    
    //  inputs from the user
    printf("Enter Book ID: ");
    scanf("%d", &bookID);
    
    printf("Enter Due Date (as a number representing days): ");
    scanf("%d", &dueDate);
    
    printf("Enter Return Date (as a number representing days): ");
    scanf("%d", &returnDate);
    
    // Calculate the days overdue
    daysOverdue = returnDate - dueDate;
    
    if (daysOverdue <= 0) {
        daysOverdue = 0;
        fine = 0;
    } else {
        // Determine the fine 
        if (daysOverdue <= 7) {
            fine = daysOverdue * 20; // 20 Sh/day for up to 7 days
        } else if (daysOverdue <= 14) {
            fine = 7 * 20 + (daysOverdue - 7) * 50; 
        } else {
            fine = 7 * 20 + 7 * 50 + (daysOverdue - 14) * 100; 
        }
    }
    
    // Display the following results
    printf("Book ID: %d\n", bookID);
    printf("Due Date: %d\n", dueDate);
    printf("Return Date: %d\n", returnDate);
    printf("Days Overdue: %d\n", daysOverdue);
    printf("Total Fine: Ksh. %d\n", fine);
    
    return 0;
}


