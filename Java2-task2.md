# Q2
# Lecturer
```java
public class Lecturer {

	private String name;
	private String dept;
	private int YearsOfExperience;
	private String nextClass;
	
	public Lecturer(String name, String dept, int yearsOfExperience,String nextClass) {
		this.name = name;
		this.dept = dept;
		YearsOfExperience = yearsOfExperience;
		this.nextClass = nextClass;
		
		
	}
	
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public String getDept() {
		return dept;
	}
	public void setDept(String dept) {
		this.dept = dept;
	}
	public int getYearsOfExperience() {
		return YearsOfExperience;
	}
	public void setYearsOfExperience(int yearsOfExperience) {
		YearsOfExperience = yearsOfExperience;
	}
	
	@Override
	public String toString()
	{
		return "Dr." + name + ", Dept = " + dept + ", Years of experience = " + YearsOfExperience;
	}
	public void introduce() {
		System.out.println("Lecturer = " + toString());
	}
	
	public void greet() {
		System.out.println("Dr."+ name + " invits you to join his next class : "+nextClass);
	}
}
```
# SeniorLecturer
```java
public class SeniorLecturer extends Lecturer{
	
	private int numberOfProjects;
	private int managedProjects;
	

	public SeniorLecturer(String name, String dept, int yearsOfExperience, String nextClass, int numberOfProjects, int managedProjects) {
		super(name, dept, yearsOfExperience, nextClass);
		
		this.numberOfProjects = numberOfProjects;
		this.managedProjects = managedProjects;
	}


	public int getNumberOfProjects() {
		return numberOfProjects;
	}


	public void setNumberOfProjects(int numberOfProjects) {
		this.numberOfProjects = numberOfProjects;
	}


	public int getManagedProjects() {
		return managedProjects;
	}


	public void setManagedProjects(int managedProjects) {
		this.managedProjects = managedProjects;
	}


	@Override
	public String toString() {
		return "Dr."  + super.getName() + ", Dept = " + super.getDept() + ", Number of managed projects = " + managedProjects;
	}
	public void introduce() {
		System.out.println("Senior Lecturer = " + toString());
	}
	
	public void greet() {
		System.out.println("Dr." + super.getName() + " invits you to work with him on all of his " + managedProjects + " projects");
	}
}
```
# Professor
```java
public class Professor extends SeniorLecturer{
	
	private int numberOfArticles;

	public Professor(String name, String dept, int yearsOfExperience, String nextClass, int numberOfProjects,
			int numberOfArticles) {
		super(name, dept, yearsOfExperience, nextClass, numberOfProjects, numberOfArticles);
		this.numberOfArticles = numberOfArticles;
	}

	public int getNumberOfPublications() {
		return numberOfArticles;
	}

	public void setNumberOfPublications(int numberOfPublications) {
		this.numberOfArticles = numberOfPublications;
	}
	
	@Override
	public String toString()
	{
		return "Prof."  + super.getName() + ", Dept = " + super.getDept() + ", Years of experience = " + getYearsOfExperience() + ", Number of Articles = " + numberOfArticles;
	}
	public void introduce() {
		System.out.println(toString());
	}
	
	public void greet() {
		System.out.println("Prof."+super.getName()+" is inviting you to join his research and writing articles ");
	}
}
```
# DeptChair
```java
public class DeptChair extends Professor {

	private int yearOfpromotionToDeptChair;
	
	public DeptChair(String name, String dept, int yearsOfExperience, String nextClass, int numberOfProjects,
			int numberOfArticles, int yearOfpromotionToDeptChair) {
		super(name, dept, yearsOfExperience, nextClass, numberOfProjects, numberOfArticles);
		this.yearOfpromotionToDeptChair = yearOfpromotionToDeptChair;
	}

	public int getYearOfpromotionToDeptChair() {
		return yearOfpromotionToDeptChair;
	}

	public void setYearOfpromotionToDeptChair(int yearOfpromotionToDeptChair) {
		this.yearOfpromotionToDeptChair = yearOfpromotionToDeptChair;
	}

	@Override
	public String toString() {
		return "Prof."  + super.getName() + ", Dept = " + super.getDept() + ", Years of experience = " + getYearsOfExperience() + "Year of promotion to DeptChair = " + yearOfpromotionToDeptChair;
	}
	public void introduce() {
		System.out.println(toString());
	}
	
	public void greet() {
		System.out.println("Prof."+super.getName()+" is inviting you to start your second degree in " + getDept() + " deparment");
	}
}
```
# ClassMain
```java
public class ClassMain {

	public static void main(String[] args) {

		Lecturer l1 = new Lecturer("John Grishman", "Architacture", 7, "Towars design");
		SeniorLecturer sl1 = new SeniorLecturer("Bob Hall", "Computer Science", 10, "JAVA", 2, 2);
		Professor p1 = new Professor("Alex Davis", "Electronic engineering", 15, "Electrical circles", 7, 4);
		DeptChair dc1 = new DeptChair("Johnathan Fisher", "Biology", 17, "Deep sea discovering", 2,
			2, 5);
		
		l1.introduce();
		sl1.introduce();
		p1.introduce();
		dc1.introduce();
		
		l1.greet();
		sl1.greet();
		p1.greet();
		dc1.greet();
		
	}
}
```