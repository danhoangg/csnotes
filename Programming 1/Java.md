Subjects/ Topics: #Java #Programming

Java source code (.java) is compiled into classes (.class) and the class file is run.

Java runs on every system via the Java virtual machine (JVM), since every machine is different at a very low level, JVM allows Java to run on every machine.

![[JVM.png]]
<b><h3>Java Template</h3></b>
Dog.java
```java
public class Dog {
	Integer age = 0;
	String name = "greg";

	public static void main(String[] args){
		Dog dog = new Dog();
		dog.info()
	}
	public void info() {
		System.out.println("Age: " + age);
		System.out.println("Name: " + name);
	}
}
```

## **Important:**

- [[Java If statements]]
- [[Java Loops]]