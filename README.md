Restaurant Management System
This is a simple Restaurant Management System written in C. It allows the user to generate, save, and view invoices for restaurant orders. The program includes features such as generating bills, displaying previous invoices, and searching for specific invoices by customer name.

Table of Contents
Features
Installation
Usage
Code Explanation
Contributing
License
Features
Generate invoices for restaurant orders.
Save invoices to a file.
View all saved invoices.
Search for specific invoices by customer name.
Installation
To run this program, you need to have a C compiler installed on your system.

Windows
Download and install MinGW.
Add the MinGW bin directory to your system's PATH.
Linux/Mac
Open your terminal.
Install GCC by running:
sh
Copy code
sudo apt-get install gcc
Compile the Program
Open your terminal or command prompt.
Navigate to the directory containing the source code.
Run the following command to compile the program:
sh
Copy code
gcc -o restaurant_management_system restaurant_management_system.c
Usage
After compiling, run the executable:

sh
Copy code
./restaurant_management_system
Follow the on-screen instructions to generate, view, and search for invoices.

Code Explanation
The code consists of several functions to handle different aspects of the Restaurant Management System. Here's a brief explanation of each part of the code:

Structures
struct items: Holds the details of each item in the order, including the item name, price, and quantity.
struct orders: Holds the details of each order, including the customer name, date, number of items, and an array of items.
Functions
generateBillHeader: Generates the header for the bill.
generateBillBody: Generates the body of the bill for each item.
generateBillFooter: Generates the footer of the bill, including the subtotal, discount, taxes, and grand total.
main: The main function contains the logic for the program, including generating invoices, viewing all invoices, searching for specific invoices, and exiting the program.
Sample Code Snippets
Generating Bill Header

c
Copy code
void generateBillHeader(char name[50], char date[30]){
    printf("\n\n");
    printf("\t      MHZ.Restaurant");
    printf("\n\t   -------------------");
    printf("\nDate:%s", date);
    printf("\nInvoice To:%s", name);
    printf("\n");
    printf("-------------------------------------------------\n");
    printf("Items\t\tQty\t\tTotal\t\t");
    printf("\n-------------------------------------------------\n");
}
Generating Bill Body

c
Copy code
void generateBillBody(char item[30], int qty, float price){
    printf("%s\t\t%d\t\t%.2f\t\t", item, qty, qty * price);
    printf("\n");
}
Generating Bill Footer

c
Copy code
void generateBillFooter(float total){
    printf("\n");
    float dis = 0.1 * total;
    float netTotal = total - dis;
    float cgst = 0.09 * netTotal, grandTotal = netTotal + 2 * cgst;
    printf("------------------------------------------------\n");
    printf("SubTotal\t\t\t %.2f\n", total);
    printf("Discount @10%%\t\t\t%.2f\n", dis);
    printf("\t\t\t\t------\n");
    printf("NetTotal\t\t\t%.2f\n", netTotal);
    printf("CGST @9%%\t\t\t%.2f\n", cgst);
    printf("SGST @9%%\t\t\t%.2f\n", cgst);
    printf("-------------------------------------------------\n");
    printf("Grand Total\t\t\t%.2f\n", grandTotal);
    printf("-------------------------------------------------\n");
}
Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

License
This project is licensed under the MIT License. See the LICENSE file for more details.
