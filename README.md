1.	Encapsulation is the bundling of data and methods that operate on the data into a single unit, called a class. It hides the internal state of an object from the outside world and only exposes the necessary functionality through well-defined interfaces. 
Create an Employee class having data members' Name, Eid, and Basic_Salary, to calculate the HRA is 20% of Basic Salary and DA is 25% of Basic salary and MA is 300 rupee. implement the following queries:
  a) Display the name and gross salary of an employee whose name starts With 'n'
  b).Display the Eid and gross salary whose Eid is equal to 107.
  c)  Count the total number of employees whose salary more than 20000/-
import java.util.Scanner;

class Employee {
    Scanner sc = new Scanner(System.in);
    int Eid, BS;
    String name;
    int MA = 300;
    double GS, HRA;

    void getData() {
        System.out.println("Ansh 2210997035");
        System.out.println("Enter Employee ID (Eid): ");
        Eid = sc.nextInt();
        System.out.println("Enter Basic Salary: ");
        BS = sc.nextInt();
        System.out.println("Enter Employee Name: ");
        name = sc.next();
    }

    void calculateSalary() {
        HRA = (BS * 20) / 100;
        GS = BS + HRA + MA;
    }

    void displayDetails() {
        // Query 1
        if (name.toLowerCase().charAt(0) == 'n') {
            System.out.println("Employee with name starting with 'n': " + name + ", Gross Salary: " + GS);
        } else {
            System.out.println("Employee with name other than first letter 'N': " + name);
        }

        // Query 2
        if (Eid == 107) {
            System.out.println("Employee with Eid 107, Gross Salary: " + GS);
        }
    }
}

public class EmployeeManagement {
    public static void main(String[] args) {
        Employee emp1 = new Employee();
        Employee emp2 = new Employee();

        System.out.println("Details for Employee 1:");
        emp1.getData();
        emp1.calculateSalary();
        emp1.displayDetails();

        System.out.println("\nDetails for Employee 2:");
        emp2.getData();
        emp2.calculateSalary();
        emp2.displayDetails();
    }
}
