1.	Encapsulation is the bundling of data and methods that operate on the data into a single unit, called a class. It hides the internal state of an object from the outside world and only exposes the necessary functionality through well-defined interfaces. 
Create an Employee class having data members' Name, Eid, and Basic_Salary, to calculate the HRA is 20% of Basic Salary and DA is 25% of Basic salary and MA is 300 rupee. implement the following queries:
  a) Display the name and gross salary of an employee whose name starts With 'n'
  b).Display the Eid and gross salary whose Eid is equal to 107.
  c)  Count the total number of employees whose salary more than 20000/-


package JavaLabPro;

import java.util.*;
public class Employee {
	String name;
	int Eid;
	static int count=0;
	double bs,hra,da,gs;
	
	void get()
	{
		Scanner sc=new Scanner(System.in);
		System.out.print("Enter the name = ");
		name=sc.next();
		System.out.print("Enter the Employee ID = ");
		Eid=sc.nextInt();
		System.out.print("Enter the Basic Salary = ");
		bs=sc.nextDouble();
	}
	void cal()
	{
		hra=20*bs/100;
		da=25*bs/100;
		gs=hra+da+300.0;
		if(name.charAt(0)=='n')
		{
			System.out.println("\nDetails of employee whose name starts from 'n' :- ");
			System.out.println("Name = "+name);
			System.out.println("Gross Salary = "+gs);
		}
		if(Eid==107)
		{
			System.out.println("\nDetails of employee whose id is 107  :- ");
			System.out.println("ID = "+Eid);
			System.out.println("Gross Salary = "+gs);
		}
		if(gs>20000)
		{
			count++;
		}
	}
	
	public static void main(String[] args) {
		int n;
		Scanner sc1=new Scanner(System.in);
		System.out.print("Enter the No. of employees = ");
		n=sc1.nextInt();
		Employee ob[]=new Employee[n];
		int i;
		for(i=0;i<n;i++)
		{
			System.out.println("Enter the details of Employeee "+(i+1));
			ob[i]=new Employee();
			ob[i].get();
		}
		for(i=0;i<n;i++)
		{
			ob[i].cal();
		}
		System.out.print("\nNo. of employees whose salary is more than 20000 are "+count);
	}

}
