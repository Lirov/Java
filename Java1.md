# Q1
``` java
public class Father {
	
	private int a;
	
	public Father(int a) {
		this.a = a;
	}
	
	public int getA() {
		return a;
	}
	public String toString() {
		String str = "a = " + getA();
		return str;
	}
}

public class Son extends Father {
	private double b;
	
	public Son(int a, double b) {
		super(a);
		this.b = b;
	}
	public Son() {
		super(2);
		b = 3.5;
	}
	public double getB() {
		return b;
	}
	public String toString() {
		String str = "a = " + getA() + " b = " + getB();
		return str;
	}
}

public class ClassMain {
	
	public static void main(String[] args) {
		
		Father x = new Father(4);
		Son    y = new Son();
		Father w = new Son(4, 2.5);
		
		System.out.println(x);
		System.out.println(y);
		System.out.println(w);		
	}
}
```
* Output:
```java
a = 4
a = 2 b = 3.5
a = 4 b = 2.5
```

# Q2

```java
public interface Solvable {
	public boolean solve() ;

	public boolean passed();
}

public class WorkWithGrade {

	public boolean solve() {
		System.out.println("WorkWithGrade::solve");
		return false;
	}
	public boolean passed() { return false; }
}

public class Exam extends WorkWithGrade implements Solvable{
	public boolean solve() {
		System.out.println("Exam::solve");
		return true;
	}
}

public class ClassMain {
	public static void main(String[] args) {
		
	Solvable ww = new Exam();
		if (ww.solve())
			System.out.println("Solved");
		else System.out.println("NOT Solved");
		
		if (ww.passed())
			System.out.println("Passed");
		else System.out.println("NOT Passed");		
	}
}
```
* Output:
```java
Exam::solve
Solved
NOT Passed
```

# Q3

```java
public class A {
	
	public int calculate() { return 5; }
	public void run() {
		System.out.println(calculate());
	}

}
public class B extends A {

    // *** change private to public ***
	public int calculate() { return 2; } 
    
}
public class ClassMain {
	public static void main(String[] args) {
	
		
		A a = new A();
		A b = new B();
		a.run();
		b.run();
		
}
}
```
* Output:
```java
// change private to public at Class B
// and the output is:
5
2

```
# Q4

```java
public class MyClass {

	private static int x;
	private static double y;
	
	public MyClass() {
		x = 2;
		y = 3.5;
	}
	
	public void updateValues(int x, double y) {
		this.x = x;
		this.y = y;
	}
	public static void print() {
		System.out.println(x);
		System.out.println(y);		
	}
}
public class ClassMain {
	public static void main(String[] args) {
		
		MyClass myClass = new MyClass();
		myClass.updateValues(5, 7.2);
		MyClass.print();
	}
}
```
* Output:

```java
5
7.2
```

# Q5

```java
public class C {
	private int a;
	
	public C(int a) {
		this.a = a;
	}
	
	public C() {
		this.a = -1;
		
	}
	public final String getStr() {
		String str = "C: " + a;
		return str;
	}
}
public class D extends C {

	private double d;
	
	public D(int x, double y) {
		super(x);
		d = y;
	}
	
	public D() {
		d = 1.1;
	}

	public String getStr1() {
		String str = super.getStr();
		str += " D: "; 
		str += d;
		return str;
	}
}
public class ClassMain {
	public static void main(String[] args) {

		C obj1 = new C();
		D obj2 = new D(2,4.6);
		System.out.println(obj1.getStr()); //"C: " -1
		System.out.println(obj2.getStr1()); //C: 2 D: 4.6
		
	}
}
```

* Output:

```java
C: -1
C: 2 D: 4.6
```

# Q6
```java
public class Store {

	private String StoreName;
	private int rent;
	
	
	public Store(String StoreName, int rent)
	{
		this.StoreName = StoreName;
		this.rent = rent;
		
	}
	
	public String get_StoreName()
	{
		return this.StoreName;
	}
	
	public void set_rent(int rent)
	{
		this.rent = rent;
	}
	
	public int get_rent()
	{
		return this.rent;
	}
	
	public boolean equals(Store Shop)
	{
		if (this.rent == Shop.get_rent()) {
			return true;
		}
		return false;
	}
}
```
# Q7
```java
public class FlowerStore extends Store{
	
	private int AmontOfOrders;
	
	public FlowerStore(String StoreName, int rent, int AmontOfOrders)
	{
		super(StoreName, rent);
		this.AmontOfOrders = AmontOfOrders;
	}

	public int getAmontOfOrders() {
		return AmontOfOrders;
	}

	public void setAmontOfOrders(int amontOfOrders) {
		AmontOfOrders = amontOfOrders;
	}
	
	@Override
	public String toString()
	{
		return "Store name : " + this.get_StoreName() + " Monthly rent : " + this.get_rent() + " Number of orders this months : " + AmontOfOrders;
	}
}
```
# Q8
```java
public class BookStore extends Store{
	
	public int NumberOfTypesOfBooks;

	public BookStore(String StoreName, int rent, int numberOfTypesOfBooks) {
		super(StoreName, rent);
		NumberOfTypesOfBooks = numberOfTypesOfBooks;
	}

	public int getNumberOfTypesOfBooks() {
		return NumberOfTypesOfBooks;
	}

	public void setNumberOfTypesOfBooks(int numberOfTypesOfBooks) {
		NumberOfTypesOfBooks = numberOfTypesOfBooks;
	}
	
}
```
# Q9
```java
import java.util.ArrayList;

public class Mall {

	public ArrayList<Store> MallStores;
	
	public Mall() {
		MallStores = new ArrayList<Store>();
	}
	
	public void add_Flower_Store(String StoreName,int rent, int AmontOfOrders)
	{
		FlowerStore Flower_Store = new FlowerStore(StoreName, rent, AmontOfOrders);
		MallStores.add(Flower_Store);
	}
	
	public void add_Book_Store(String StoreName, int rent, int numberOfTypesOfBooks)
	{
		BookStore Book_Store = new BookStore(StoreName, rent, numberOfTypesOfBooks);
		MallStores.add(Book_Store);
	}
	
	public void printMallInfo() {
	
		int numberOfBookStores = 0;
		int rentSum = 0;
		
		for (Store Shop : MallStores) {
			
			rentSum+= Shop.get_rent();
					
			if(Shop instanceof BookStore)
				numberOfBookStores++;
		}
		System.out.println("Rent Summary : " + rentSum + ", Number of book stores : " + numberOfBookStores);
	}
}
```
# ClassMain
```java
public class ClassMain {

	public static void main(String[] args) {

		Mall m1 = new Mall();
		
		m1.add_Book_Store("Books 'R' Us", 4300, 10296);
		m1.add_Book_Store("Books For You", 5200, 15372);
		m1.add_Flower_Store("Beautiful Flowers", 3700, 750);
		Store s1 = new Store("PetShop", 7200);
		Store s2 = new Store("The Home and office Shop", 11200);
		
		m1.printMallInfo();
		
	}
}
```
