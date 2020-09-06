# Q1
# Person
```java
public class Person {

	private String name;
	private String Id;
	public Person(String name, String id) {
		
		this.name = name;
		Id = id;
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public String getId() {
		return Id;
	}
	@Override
	public String toString() {
		return "Name = " + name + ", Id = " + Id;
	}	
}
```
# Student
```java
public class Student extends Person{
	
	private String dept;
	private int year;
	public Student(String name, String id, String dept, int year) {
		
		super(name,id);
		this.dept = dept;
		this.year = year;
	}
	public String getDept() {
		return dept;
	}
	public void setDept(String dept) {
		this.dept = dept;
	}
	public int getYear() {
		return year;
	}
	public void setYear(int year) {
		this.year = year;
	}
	@Override
	public String toString() {
		return "Student: " + super.toString() + ", Department = " + dept + ", Year=" + year;
	}
	public void introduce() {
		System.out.println(this.toString());
	}
	public String studentInfo() {
		return "Student: " + super.toString() + ",dept = " + dept + ", year = " + year;
		
	}
}
```
# Employee
```java
public class Employee extends Person{

	
	private String workplace;
	private String job;
	public Employee(String name, String id, String workplace, String job) {
		
		super(name,id);
		this.workplace = workplace;
		this.job = job;
	}
	
	public String getWorkplace() {
		return workplace;
	}
	public void setWorkplace(String workplace) {
		this.workplace = workplace;
	}
	public String getJob() {
		return job;
	}
	public void setJob(String job) {
		this.job = job;
	}
	
	@Override
	public String toString() {
		return "Employee: " + super.toString() + "," + " Workplace = " + workplace + " , Job = " + job;
	}
	public void introduce() {
		System.out.println(this.toString());
	}
	
	public String workInfo()
	{
		return super.toString() + " workplace = " + workplace + " job = " + job;
	}
}
```
# StudentEmployee
```java
public class StudentEmployee extends Person{

	private String dept;
	private int year;
	private String workplace;
	private String job;
	
	
	public StudentEmployee(String name, String id, String dept, int year, String workplace, String job) {
		super(name,id);
		this.dept = dept;
		this.year = year;
		this.workplace = workplace;
		this.job = job;
	}


	public String getDept() {
		return dept;
	}


	public void setDept(String dept) {
		this.dept = dept;
	}


	public int getYear() {
		return year;
	}


	public void setYear(int year) {
		this.year = year;
	}


	public String getWorkplace() {
		return workplace;
	}


	public void setWorkplace(String workplace) {
		this.workplace = workplace;
	}


	public String getJob() {
		return job;
	}


	public void setJob(String job) {
		this.job = job;
	}


	@Override
	public String toString() {
		return "StudentEmployee: " + super.toString() + ", Department = " + dept + ", Year=" + year + "," + " Workplace = " + workplace + ", Job = " + job;
	}
	public void introduce() {
		System.out.println(this.toString());
	}
	
	public String workInfo()
	{
		return super.toString() + " workplace = " + workplace + " job = " + job;
	}
}
```
# ClassMain
```java
public class ClassMain {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		Employee e1 = new Employee("Liron", "33222", "Apple", "Programmer");
		Student s1 = new Student("Brouce", "11443", "Software engineering", 2009);
		StudentEmployee se1 = new StudentEmployee("David", "22678", "Computer science", 2012,"Intel","Research and development");
		
		e1.introduce();
		s1.introduce();
		se1.introduce();
		
		e1.workInfo();
		s1.studentInfo();
		se1.workInfo();
	}
}
```