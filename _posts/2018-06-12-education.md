---
layout: post
title:  "Java 8- Lambda Expression"
author: Lipika
categories: [ Jekyll, tutorial ]
image: assets/images/3.jpg
---

Lambda Expression Syntax
(argument-list) -> {body}

Argument-list: Can be empty or non-empty as well.

Arrow-token: Used to link arguments-list and body of expression.

Body: Contains expressions and statements for lambda expression.

Ex - (x,y)->(x+y)

## Lammda Expression using Comparator Example

Comparator interface is used to order the objects of user-defined class. This interface is present in java.util package and contains 2 methods compare(Object obj1, Object obj2) and equals(Object element). Using comparator, we can sort the elements based on data members.

## Give a Try
Write a program using lambda expression and collections sort to sort a list of employee objects with the employee name in ascending order. Define Employee class with parameters ID, Name, Age.


## 1. Sort without Lambda

Example to compare the Employee objects using their Age. 

Step 1: We need to create Employee Class with parameters ID,Name,Age.
```
package test;

public class Employee {
	
	private int id;
	private String name;
	private int age;
	
	
	public Employee(int id, String name, int age) {
		super();
		this.id = id;
		this.name = name;
		this.age = age;
	}
	public int getId() {
		return id;
	}
	public void setId(int id) {
		this.id = id;
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public int getAge() {
		return age;
	}
	public void setAge(int age) {
		this.age = age;
	}
	@Override
	public String toString() {
		return "Employee [id=" + id + ", name=" + name + ", age=" + age + "]";
	}

```
Step 1: Normally, you use Collections.sort and pass an anonymous Comparator class like this :

```
package test;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

public class TestEmployee {

	public static void main(String[] args) {
		
		List<Employee> listEmp = getEmployees();
		System.out.println("Before Sort"+ listEmp);
		
		Collections.sort(listEmp, new Comparator<Employee>() {

			@Override
			public int compare(Employee o1, Employee o2) {
				return o1.getAge()-o2.getAge();
			}
			
		});
		
		System.out.println("After sort:");
		for (Employee emp : listEmp){
			System.out.println(emp);
		}
		
	}
	
	private static List<Employee> getEmployees() {
		List<Employee> emp = new ArrayList<Employee>();
		emp.add(new Employee(123,"Admin",50));
		emp.add(new Employee(125,"Ritika",22));
		emp.add(new Employee(122,"Omny",30));
		emp.add(new Employee(126,"Kamla",25));
		emp.add(new Employee(127,"Dashe",26));
		
		return emp;
		
	}

}

```

When the sorting requirement is changed, you just pass in another new anonymous Comparator class :
```
// Sort with name

Collections.sort(listEmp , new Comparator<Employee>() {

			@Override
			public int compare(Employee o1, Employee o2) {
				return o1.getName().compareTo(o2.getName());
			}
			
		});

```

## 2. Sort with Lambda
```
In Java 8, the List interface is supports the sort method directly, no need to use Collections.sort anymore.

listEmp.sort(new Comparator<Employee>() {

			@Override
			public int compare(Employee arg0, Employee arg1) {
				return arg0.getName().compareTo(arg1.getName());
			}
			
		});
```

Lambda Expression example
```
package test;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

public class TestEmployee {

	public static void main(String[] args) {
		
		List<Employee> listEmp = getEmployees();
		System.out.println("Before Sort"+ listEmp);
		//lambda here 
		listEmp.sort((Employee o1,Employee o2) -> o1.getAge()-o2.getAge());
		// in Java 8 only lambda to print list
		listEmp.forEach((employee) -> System.out.println(employee));
        
        //Sort by id
        //Parameter type is optional
        listEmp.sort((o1,o2) -> o1.getId()-o2.getId());
		listEmp.forEach((employee) -> System.out.println(employee));
	}
	
	private static List<Employee> getEmployees() {
		List<Employee> emp = new ArrayList<Employee>();
		emp.add(new Employee(123,"Admin",50));
		emp.add(new Employee(125,"Ritika",22));
		emp.add(new Employee(122,"Omny",30));
		emp.add(new Employee(121,"Kamla",25));
		emp.add(new Employee(125,"Dashe",26));
		
		return emp;
		
	}

}
```

