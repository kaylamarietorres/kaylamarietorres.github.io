---
layout: project
type: project
image: img/toyshop.jpeg
title: "Toyshop"
date: 2022
published: true
labels:
  - Java Basics
  - Object-oriented Programming
summary: "A toyshop project I created for ICS 111."
---

<img class="img-fluid" src="../img/toyshop.jpeg">

A Java program that simulates a Toyshop including classes of Customer, Employee, Person, Product, ToyShop and Transaction. This project shows proficiency in object-oriented programming with Java, and with this code you can build other shops as well.  

The Customer class represents a customer of the shop. With this class you can create a customer to purchase items within this shop, logging down information about the customer such as name, customer ID, and email.
The Employee class represents an employee of the shop. With this class you can create employees for this shop, recording information such as name, department, and employee ID.
The Product class represents an item for sale in the shop. With this class you can create a product with a name, description, price, and product ID. 
The transaction class represents a transaction in this shop. A transaction will include transaction ID, date of purchase, employee name, customer name, product name, and purchase method. 
The ToyShop class has a menu where you can edit the shop from various choices; add new employee, add new customer, add new product, edit employee, edit customer, edit product, add new transaction, display all transactions, and exit. 




Here is the code for the toy shop class:
```cpp
byte ADCRead(byte ch)
{

/**Main class with main method
 * 
 * @author kayla  */
import java.util.ArrayList;
import java.util.Scanner;

public class ToyShop {

	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);

		// creating an ArrayList of employees, customers, products, and transactions
		ArrayList<Employee> myEmployees = new ArrayList<Employee>();
		ArrayList<Customer> myCustomers = new ArrayList<Customer>();
		ArrayList<Product> myProducts = new ArrayList<Product>();
		ArrayList<Transaction> storeTransactions = new ArrayList<Transaction>();

		// menu
		boolean loop = true;
		while (loop = true) {
			//while loop to keep the program running
			System.out.println("Please select from the following options:");
			System.out.println("1. Add new employee");
			System.out.println("2. Add new customer");
			System.out.println("3. Add new product");
			System.out.println("4. Edit employee");
			System.out.println("5. Edit customer");
			System.out.println("6. Edit product");
			System.out.println("7. Add new transaction");
			System.out.println("8. Display all transactions");
			System.out.println("9. Exit");
			int choice = input.nextInt();
			input.nextLine();
			
			//if statements to delegate which choice is made from menu 
			if (choice == 1) {
				// adding a new employee
				System.out.println("Enter the Employee's first name: ");
				String f = input.nextLine();
				System.out.println("Enter the Employee's last name: ");
				String l = input.nextLine();
				System.out.println("Enter the Employee's department: ");
				String d = input.nextLine();
				myEmployees.add(new Employee(f, l, d));
				System.out.println("Employee successfully added!");
			} else if (choice == 2) {
				// adding a new customer
				System.out.println("Enter the Customer's first name: ");
				String f = input.nextLine();
				System.out.println("Enter the Customer's last name: ");
				String l = input.nextLine();
				System.out.println("Enter the Customer's email: ");
				String email = input.nextLine();
				myCustomers.add(new Customer(f, l, email));
				System.out.println("Customer successfully added!");
			} else if (choice == 3) {
				// adding a new product
				System.out.println("Enter the Product's name: ");
				String n = input.nextLine();
				System.out.println("Enter the Product's description: ");
				String d = input.nextLine();
				System.out.println("Enter the Product's price: ");
				double p = input.nextDouble();
				myProducts.add(new Product(n, d, p));
				System.out.println("Product successfully added!");
			} else if (choice == 4) {
				// editing an employee
				System.out.println("EMPLOYEE LIST: ");
				for (int i = 0; i < myEmployees.size(); i++) {
					System.out.println(i + " - " + myEmployees.get(i).getFirstName() + " "
							+ myEmployees.get(i).getLastName()
							+ " [" + myEmployees.get(i).getDepartment() + "]");
				}
				System.out.println("Enter the ID number of the employee you want to edit: ");
				int number = input.nextInt();
				if (number < myEmployees.size()) {
					System.out.println("Enter the Employee's new first name: ");
					String f = input.nextLine();
					input.nextLine();
					System.out.println("Enter the Employee's new last name: ");
					String l = input.nextLine();
					System.out.println("Enter the Employee's new department: ");
					String d = input.nextLine();
					myEmployees.get(number).setFirstName(f);
					myEmployees.get(number).setLastName(l);
					myEmployees.get(number).setDepartment(d);
					System.out.println("Employee successfully edited!");

				} else {
					// invalid user input
					System.out.println("Sorry! Invalid number! ");
					break;
				}
			} else if (choice == 5) {
				// EDITING A CUSTOMER

				// print list of customers with their emails
				System.out.println("CUSTOMER LIST: ");
				for (int i = 0; i < myCustomers.size(); i++) {
					System.out.println(i + " - " + myCustomers.get(i).getFirstName() + " "
							+ myCustomers.get(i).getLastName()
							+ "[" + myCustomers.get(i).getEmail() + "]");
				}
				// choose ID number of customer to edit
				System.out.println("Enter the ID number of the customer you want to edit: ");
				int number = input.nextInt();

				// check that customer ID number is valid
				if (number < myCustomers.size()) {
					System.out.println("Enter the Customer's new first name: ");
					String f = input.nextLine();
					input.nextLine();
					System.out.println("Enter the Customer's new last name: ");
					String l = input.nextLine();
					System.out.println("Enter the Customer's new email: ");
					String email = input.nextLine();
					myCustomers.get(number).setFirstName(f);
					myCustomers.get(number).setLastName(l);
					myCustomers.get(number).setEmail(email);
					System.out.println("Customer successfully edited!");
				} else {
					// invalid user input
					System.out.println("Sorry! Invalid number! ");
				}
			} else if (choice == 6) {
				// EDITING A PRODUCT

				// print list of products with their description
				System.out.println("PRODUCT LIST: ");
				for (int i = 0; i < myProducts.size(); i++) {
					System.out.println(i + " - " + myProducts.get(i).getProductName() + "description: "
							+ myProducts.get(i).getDesc());
				}
				// choose ID number of product you want to edit
				System.out.println("Enter the ID number of the product you want to edit: ");
				int number = input.nextInt();

				// check that it is a valid product ID number
				if (number < myProducts.size()) {
					System.out.println("Enter the Product's new name: ");
					String n = input.nextLine();
					input.nextLine();
					System.out.println("Enter the Product's new description: ");
					String d = input.nextLine();
					System.out.println("Enter the Product's new price: ");
					Double p = input.nextDouble();
					myProducts.get(number).setProductName(n);
					myProducts.get(number).setDesc(d);
					myProducts.get(number).setPrice(p);
					System.out.println("Product information successfully edited!");
				} else {
					System.out.println("Sorry! Invalid number! ");
				}
			} else if (choice == 7) {
				// ADD NEW TRANSACTION

				// ask for date of transaction
				System.out.println("Enter the date of transaction: ");
				String date = input.nextLine();

				// getting the employee ID
				System.out.println("Enter the Employee's ID who sold the product: ");
				
				// display all employees to choose from 
				System.out.println("EMPLOYEES: ");
				for (int i = 0; i < myEmployees.size(); i++) {
					System.out.println(myEmployees.get(i).toString());
				}
				int employeeID = input.nextInt();

				// initializing employee ID numbers
				int employeeNumber = 0, customerNumber = 0, productNumber = 0;

				// making sure its a valid employee number
				for (int i = 0; i < myEmployees.size(); i++) {
					if (myEmployees.get(i).getEmployeeID() == employeeID) {
						employeeNumber = i;
					}
				}
				// getting the customer ID
				System.out.println("Enter the Customer's ID who bought the product: ");
				
				// display all customer ID's to choose from
				System.out.println("CUSTOMERS: ");
				for (int i = 0; i < myCustomers.size(); i++) {
					System.out.println(myCustomers.get(i).toString());
				}
				int custID = input.nextInt();
				
				//making sure its a valid customer number
				for (int i = 0; i < myCustomers.size(); i++) {
					if (myCustomers.get(i).getCustomerID() == custID) {
						customerNumber = i;
					}
				}
				//Printing out list of product and getting product ID input from user 
				System.out.println("PRODUCT LIST: ");
				for (int i = 0; i < myProducts.size(); i++) {
					System.out.println(i + " - " + myProducts.get(i).getProductName() + "\nDescription: " +myProducts.get(i).getDesc());
				}
				System.out.println("Enter the Product's ID: ");
				int productID = input.nextInt();
				
				//setting product number as product ID
				for (int i = 0; i < myProducts.size(); i++) {
					if (myProducts.get(i).getProductID() == productID) {
						productNumber = i;
					}
				}
				// getting the purchase method
				System.out.println("Enter the Purchase Method(cash or card): ");
				String purchaseMethod = input.next();

				// check if product, customer, and employee number are valid
				if (productNumber >= 0 && customerNumber >= 0 && employeeNumber >= 0) {
					
					//if valid, add new transaction
					storeTransactions.add(new Transaction(date, myEmployees.get(employeeNumber),
							myCustomers.get(customerNumber), myProducts.get(productID), purchaseMethod));
					System.out.println("New transaction added successfully! ");
				}
			} else if (choice == 8) {
				// display all transactions
				System.out.println("TRANSACTIONS: ");
				for (int i = 0; i < storeTransactions.size(); i++) {
					System.out.println(storeTransactions.get(i).toString());
				}
			} else if (choice == 9) {
				// EXIT
				System.exit(0);
			} else {
				System.out.print("Sorry invalid input");
			}
		}
	}
}
    
}
```
