<img src="../images/Back-end/JavaCompile.png" width=800 />

<img src="../images/Back-end/jdk.png" width=800 />

<img src="../images/Back-end/data type.png" width=800 />

<img src="../images/Back-end/primitive vs reference.png" width=800 />

<br>

# variables

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        System.out.print("I love ice cream\n");
        int x; //declaration
        int y = 123; // initialization
        System.out.println("my number is: " + y);

        long z = 123123125364747L;

        Scanner scanner = new Scanner(System.in);

        System.out.println("What is your name?");
        String name = scanner.nextLine();
        System.out.println("how old are you?");
        int age = scanner.nextInt();
        scanner.nextLine();
        System.out.println("what is your favorite food?");
        String food = scanner.nextLine();

        System.out.println("hello " + name);
        System.out.println("You are "+age+" years old");
        System.out.println("your favorite food is: "+food);
    }
}
```

# GUI

```java
import javax.swing.JOptionPane;

public class Main {
    public static void main(String[] args) {
        String name = JOptionPane.showInputDialog("Enter your name");
        JOptionPane.showMessageDialog(null, "Hello! " + name);

        int age = Integer.parseInt(JOptionPane.showInputDialog("Enter your age"));
        JOptionPane.showMessageDialog(null, "You are: " + age + " years old");

        double height = Double.parseDouble(JOptionPane.showInputDialog("Enter your height"));
        JOptionPane.showMessageDialog(null, "Your height: " + height + " cm");
    }
}
```

# Math

```java
import javax.swing.JOptionPane;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        double x;
        double y;
        double z;

        Scanner scanner = new Scanner(System.in);

        System.out.println("enter side x: ");
        x = scanner.nextDouble();
        System.out.println("enter side y: ");
        y = scanner.nextDouble();

        z = Math.sqrt(x*x + y*y);
        System.out.println(z);

        scanner.close();
    }
}
```

# Random

```java
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        Random random = new Random();

//        int x = random.nextInt(6)+1;
//        double y = random.nextDouble();

        boolean z = random.nextBoolean();
        System.out.println(z);


    }
}
```

# if statement

```java
public class Main {
    public static void main(String[] args) {

int age = 18;
if(age>=18){
    System.out.println("you are adult");
}
else {
    System.out.println("you are not an adult");
}
    }
}
```

# switches

```java
public class Main {
    public static void main(String[] args) {

        String day = "pizza";

        switch (day) {
            case "Sunday":
                System.out.println("it is sunday");
                break;
            case "Monday":
                System.out.println("it is monday");
                break;
            case "Tuesday":
                System.out.println("it is Tuesday");
                break;
            default:
                System.out.println("that is not a day");
        }
    }
}
```

# logical operators: && || !

```java
public class Main {
    public static void main(String[] args) {

        int temp = 25;

        if(temp>30){
            System.out.println("it is hot outside");
        }
        else if(temp>=20 && temp<=30){
            System.out.println("it is warm outside");
        }
        else {
            System.out.println("it is cold outside");
        }

    }
}
```

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.println("you are playing a game! press q or Q to quit");
        String response = scanner.next();

        if (response.equals("q") || response.equals("Q")) {
            System.out.println("you quit the game");
        } else {
            System.out.println("You are still playing the game");
        }
    }
}
```

# while loop

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        String name = "";

        while(name.isBlank()){
            System.out.print("Please type your name: ");
            name = scanner.nextLine();
        }
        System.out.println("hello "+name);
    }
}
```

the other one is **do while** loop which executes once after check the condition

# for loop

```java
public class Main {
    public static void main(String[] args) {
        // for loop executes code limited times
        for (int i = 0; i <= 10; i++) {
            System.out.println(i);
        }
    }
}
```

# nested loop

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        int rows;
        int columns;
        String symbol = "";

        System.out.println("Enter # of rows: ");
        rows = scanner.nextInt();
        System.out.println("Enter # of columns: ");
        columns = scanner.nextInt();
        System.out.println("Enter your symbol: ");
        symbol = scanner.next();

        for(int i = 1; i<= rows; i++){
            System.out.println();
            for(int j = 1; j<=columns; j++){
                System.out.print(symbol);
            }
        }
    }
}
```

# array

```java

public class Main {
    public static void main(String[] args) {
        String[] cars = {"Camaro", "Corvette", "Tesla"};
        cars[0] = "Mustang";
        System.out.println(cars[0]);
    }
}
```

or assign the amount of elements first:

```java

public class Main {
    public static void main(String[] args) {
        String[] color = new String[3]; // create 3 elements in the array

        color[0] = "red";
        color[1] = "green";
        color[2] = "blue";

        for(int i = 0; i< color.length; i++){
            System.out.println(color[i]);
        }
    }
}
```

# 2D array

<img src="../images/Back-end/2dArray.png" width=600>

```java

public class Main {
    public static void main(String[] args) {

        String[][] cars = new String[3][3];

        cars[0][0]= "Camaro"; // like rows and columns
        cars[0][1]= "Corvette";
        cars[0][2]= "Silverado";
        cars[1][0]= "DDF";
        cars[1][1]= "fasdfa";
        cars[1][2]= "asgaga";
        cars[2][0]= "qwrwt";
        cars[2][1]= "agagb";
        cars[2][2]= "hgsfdh";

        for(int i=0; i< cars.length; i++){
            System.out.println();
            for(int j= 0; j <cars[i].length; j++){
                System.out.print(cars[i][j]+" ");
            }
        }
    }
}
```

or we can assign like this:

```java
String[][] cars = {
    {"Camaro", "Corvette", "Silverado"},
    {"DDF", "fasdfa", "asgaga"},
    {"qwrwt", "agagb", "hgsfdh"}
};
```

# String methods

```java
    String name = "Bro";

    boolean result = name.equals("Bro");

    int result = name.length();

    char result = name.charAt(0);

    boolean result = name.isEmpty();

    String result = name.toUpperCase();

    String result = name.toUpperCase();

    String result = name.replace("o", "e");

```

# wrapper class

a way to use primitive types as **reference** types, because reference data types contain useful methods, and can be used with collections

primitive--------------wrapper

boolean----------------Boolean

char-------------------Character

int--------------------Integer

double-----------------Double

```java
        // autoboxing
        // unboxing

        Boolean a = true;
        Character b = "@";
        Integer c = 123;
        Double d = 3.14;
        String e = "Bros";
```

# ArrayList

a resizable array, elements can be added and removed after compilation phase. They only store **reference data type**

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {

        ArrayList<String> food = new ArrayList<String>();

        food.add("pizza");
        food.add("hamburger");
        food.add("hotdog");

        // methods:
        food.set(0, "sushi");
        food.remove(2);
        food.clear();

        for(int i=0; i<food.size(); i++){
            System.out.println(food.get(i));
        }
    }
}
```

# 2D ArrayList

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<ArrayList<String>> groceryList = new ArrayList<>();

        ArrayList<String> bakeryList = new ArrayList<>();
        bakeryList.add("pasta");
        bakeryList.add("garlic bread");
        bakeryList.add("donuts");

        ArrayList<String> vegeList = new ArrayList<>();
        vegeList.add("tomato");
        vegeList.add("carrot");

        groceryList.add(bakeryList);
        groceryList.add(vegeList);
        System.out.println(groceryList);
        System.out.println(groceryList.get(0));
        System.out.println(groceryList.get(0).get(0));
    }
}
```

# for each

iterate elements in an array/collection, less steps than for loop, but less flexible

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
//        String[] animals = {"cat", "dog", "rat", "bird"};
        ArrayList<String> animals = new ArrayList<String>();

        animals.add("cat");
        animals.add("dog");
        animals.add("rat");
        animals.add("bird");


        for (String i : animals) {
            System.out.println(i);

        }
    }
}
```

# customize methods

```java
public class Main {
    public static void main(String[] args) {
        String name = "fanpeng";
        hello(name);
    }

   static void hello(String title) {
        System.out.println("hello " + title);
    }

}
```

```java
public class Main {
    public static void main(String[] args) {
        String name = "fanpeng";
        int age = 21;
        hello(name, age);
    }

   static void hello(String title, int age) {
        System.out.println("hello " + title);
       System.out.println("You are " + age );
    }

}
```

```java

public class Main {
    public static void main(String[] args) {
        int x = 3;
        int y = 4;
        System.out.println(add(x, y));
    }

    static int add(int x, int y) {
        return x + y;
    }

}
```

# overloaded methods

methods that have the same name but have different parameters

```java
public class Main {
    public static void main(String[] args) {
        int total = add(1, 3, 5);
        System.out.println(total);
    }

    static int add(int a, int b) {
        System.out.println("this is overloaded method 1");
        return a + b;
    }

    static int add(int a, int b, int c) {
        System.out.println("this is overloaded method 2");
        return a + b + c;
    }

    static int add(int a, int b, int c, int d) {
        System.out.println("this is overloaded method 3");
        return a + b + c + d;
    }
}
```

# printf() method

2 arguments: format string + (object/variable/value)

```java
public class Main {
    public static void main(String[] args) {
        System.out.printf("this is a format string %d", 123); // this is a format string 123
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        boolean myBoolean = true;
        char myChar = '@';
        String myString = "Fanpeng";
        int myInt = 50;
        double myDouble = 1000;

        System.out.printf("%b 👈here is the result", myBoolean);
        System.out.printf("%c 👈", myChar);

        //can also set width:
        System.out.printf("%10c 👈", myChar);
        //can also set the precision of float and double:
        System.out.printf("%.2f", myDouble);
        // display positive or negetive number:
        System.out.printf("You have this much money: %+f", myDouble);
        // group separator for numbers:

    }
}
```

# final keyword

assign variable cannot be changed later

```java
public class Main {
    public static void main(String[] args) {
        final double PI = 3.14159;
        System.out.println(PI);
    }
}
```

# OOP

```java
public class Car {
    String make = "Chevrolet";
    String model = "Corvette";
    int year = 2023;
    String color = "blue";
    double price = 50000.00;

    void drive(){
        System.out.println("you drive the car");
    }
    void brake(){
        System.out.println("you step on the brakes");
    }
}
```

# constructors

```java
public class Main {
    public static void main(String[] args) {
        Human human1 = new Human("Rick", 65,70);
        System.out.println(human1.age);

        Human human2 = new Human("Lisa", 20, 60);
        System.out.println(human2.name);

        human2.eat();
        human1.drink();
    }
}

import org.w3c.dom.ls.LSOutput;

public class Human {
    String name;
    int age;
    double weight;
    Human(String name, int age, double weight){
        this.name = name;
        this.age = age;
        this.weight = weight;
    }

    // method:
    void eat(){
        System.out.println(this.name+ " is eating");
    }
    void drink(){
        System.out.println(this.name+ " is drinking");
    }
}
```

# local & global

local: declared inside a method,
global: declared outside of a method, but within a class visible to all parts of a class

```java
import java.util.Random;

public class Dice {

    Dice(){
        Random random = new Random();
        int number = 0;
        roll(random, number);
    }
    void roll(Random random, int number){
        number = random.nextInt(6)+1;
        System.out.println(number);
    }
}
```

# overloaded constructor

it allows to create objects in different ways. For example, one constructor might require only one parameter, while another might require two or more.

```java
public class Pizza {
    String bread;
    String sauce;
    String cheese;
    String topping;

    Pizza(String bread, String sauce) {
        this.bread = bread;
        this.sauce = sauce;
    }
    Pizza(String bread, String sauce, String cheese) {
        this.bread = bread;
        this.sauce = sauce;
        this.cheese = cheese;
    }
    Pizza(String bread, String sauce, String cheese, String topping) {
        this.bread = bread;
        this.sauce = sauce;
        this.cheese = cheese;
        this.topping = topping;
    }
}
```

# toString()

```java
public class Main {
    public static void main(String[] args) {

        Car car = new Car();
        System.out.println(car); //Car@30f39991   the address in the memory
    }
}
```

usage: return the string representation of attributes of the object:

```java
public class Main {
    public static void main(String[] args) {

        Car car = new Car();
        System.out.println(car.toString());
    }
}


public class Car {
    String make = "Chevrolet";
    String model = "Corvette";
    int year = 2023;
    String color = "blue";
    double price = 50000.00;

    public String toString() {
        return make + "\n"+model+"\n"+color+"\n"+year;
    }
}
```

# array of objects

first way:

```java
public class Main {
    public static void main(String[] args) {

        // array of Food objects called fridge, hold 3 elements:
        Food[] fridge = new Food[3];

        Food food1  = new Food("pizza");
        Food food2  = new Food("cream");
        Food food3  = new Food("hotdog");

        fridge[0] = food1;
        fridge[1] = food2;
        fridge[2] = food3;

        System.out.println(fridge[0].name);
        System.out.println(fridge[1].name);
        System.out.println(fridge[2].name);
    }
}
```

another way:

```java
public class Main {
    public static void main(String[] args) {

        Food food1  = new Food("pizza");
        Food food2  = new Food("cream");
        Food food3  = new Food("hotdog");

        Food[] fridge = {food1, food2, food3};

        System.out.println(fridge[0].name);
        System.out.println(fridge[1].name);
        System.out.println(fridge[2].name);
    }
}
```

# object passing

pass object as argument

```java
public class Main {
    public static void main(String[] args) {

        //create an instance of Garage object:
        Garage garage = new Garage();

        Car car1 = new Car("BMW");
        Car car2 = new Car("Tesla");

        garage.park(car1);
        garage.park(car2);
    }
}


public class Garage {

    void park(Car car1){
        System.out.println(car1.name + " is parking in the garage.");
    }
}



public class Car {
    String name;

    Car(String name) {
        this.name = name;
    }
}
```

# static keyword

(class variable)

used to declare members (variables and methods) that belong to the class itself, rather than to instances (objects) of the class.

static variable & static method

```java
public class Friend {
    String name;
    static int numberOfFriends;

    Friend(String name){
        this.name = name;
        numberOfFriends++;
    }

      static void displayFriends(){
        System.out.println("You have "+numberOfFriends+" friends");
    }
}


public class Main {
    public static void main(String[] args) {

        Friend friend1 = new Friend("Lisa");
        Friend friend2 = new Friend("Bob");
        Friend friend3 = new Friend("John");

        System.out.println(Friend.numberOfFriends);

        Friend.displayFriends();
    }
}
```

static vs instance

```java
public class MyClass {
    static int staticVar; // Static variable
    int instanceVar; // Instance variable

    public static void main(String[] args) {
        MyClass.staticVar = 10; // Accessing static variable directly

        MyClass obj1 = new MyClass();
        MyClass obj2 = new MyClass();

        obj1.instanceVar = 20; // Accessing instance variable through object
        obj2.instanceVar = 30; // Accessing instance variable through object
    }
}
```

# inheritance

one class receive attributes and methods from another class.

```java
public class Main {
    public static void main(String[] args) {

        Car car = new Car();

        car.go();

        Bicycle bike = new Bicycle();

        bike.stop();

        System.out.println("It has " + car.doors + " doors.");
    }
}



public class Vehicle {
    double speed;

     void go(){
        System.out.println("The vehicle is moving.");
    }
    void stop(){
        System.out.println("The vehicle stopped.");
    }
}


public class Bicycle extends Vehicle {
    // receive attributes and methods from Vehicle

    // has its own unique attributes
    int wheels = 2;
    int pedals = 2;
}


public class Car extends Vehicle {

    // has its own unique attributes
    int wheels = 4;
    int doors = 4;
}
```

# method overriding

```java
public class Main {
    public static void main(String[] args) {

        Dog dog = new Dog();
        dog.speak(); // bark bark

        Animal animal = new Animal();
        animal.speak(); // the animal is speaking.
        // they will use the closest method
    }
}



public class Animal {

    void speak() {
        System.out.println("the animal is speaking.");
    }
}


public class Dog extends Animal {

    //overriding the method from Animal:
    @Override
    void speak() {
        System.out.println("bark bark");
    }

}
```

# super keyword

superclass(parent) of an object, similar to "this" keyword

```java
public class Main {
    public static void main(String[] args) {

        Hero hero1 = new Hero("Batman", 42, "$$$");
        Hero hero2 = new Hero("Spiderman", 30, "fly");

        System.out.println(hero1.name + " " + hero1.age + " " + hero1.power);
        System.out.println(hero2.name + " " + hero2.age + " " + hero2.power);

        System.out.println(hero2.toString());
    }
}


public class Person {
    String name;
    int age;

    Person(String name, int age){
        this.name = name;
        this.age = age;
    }

    public String toString() {
        return this.name + "\n" + this.age + "\n";
    }
}


public class Hero extends Person {
    String power;

    Hero(String name, int age, String power) {
        super(name, age);
        this.power = power;
    }

    public String toString() {
        return super.toString()+this.power;
    }
}
```

# abstraction

Abstract Classes:

a class that cannot be instantiated on its own. It serves as a blueprint for other classes to extend from.

Abstract classes may contain both regular (concrete) methods with implementations and abstract methods without implementations.

Abstract Methods:

a method declared without an implementation (body). It provides a signature (name and parameters) but no actual code.

```java
// Animal is an abstract class
abstract class Animal {
    abstract void makeSound(); // Abstract method, can only be implemented in child classes

void eat() {
    System.out.println("Animal is eating");
} // regular method
}

class Dog extends Animal {
    @Override // it is forced to override in the child Dog class
    void makeSound() {
        System.out.println("Dog barks");
}
}

class Cat extends Animal {
    @Override // it is forced to override in the child Cat class
    void makeSound() {
        System.out.println("Cat meows");
}
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound(); // Output: Dog barks
        dog.eat(); // Output: Animal is eating

        Cat cat = new Cat();
        cat.makeSound(); // Output: Cat meows
        cat.eat();       // Output: Animal is eating
    }

}
```

# access modifier

public, protected, private

# encapsulation

attributes of a class will be hidden or private, can be accessed via (getters, setters)

```java
public class Main {
    public static void main(String[] args) {

        Car car = new Car("Chevrolet", "Camaro", 2021);

        System.out.println(car.getMake());
        System.out.println(car.getModel());
        System.out.println(car.getYear());

        car.setYear(2024);
        System.out.println(car.getMake());
        System.out.println(car.getModel());
        System.out.println(car.getYear());
    }
}


public class Car {

    private String make;
    private String model;
    private int year;

    Car(String make, String model, int year) {
        this.setMake(make);
        this.setModel(model);
        this.setYear(year);
    }

    //getter methods: to change private attribute
    public String getMake(){
        return make;
    }
    public String getModel(){
        return model;
    }
    public int getYear(){
        return year;
    }

    // setter methods:
    public void setMake(String make){
        this.make = make;
    }
    public void setModel(String model){
        this.model = model;
    }
    public void setYear(int year){
        this.year = year;
    }
}
```

# copy objects

```java
public class Main {
    public static void main(String[] args) {

        Car car1 = new Car("Chevrolet", "Camaro", 2021);
        Car car2 = new Car("Ford", "Mustang", 2022);

        // use the copy method: now they have different address in memory but have same attributes:
        car2.copy(car1);

        System.out.println(car1);
        System.out.println(car2);
        System.out.println();
        System.out.println(car1.getMake());
        System.out.println(car1.getModel());
        System.out.println(car1.getYear());
        System.out.println();
        System.out.println(car2.getMake());
        System.out.println(car2.getModel());
        System.out.println(car2.getYear());
    }
}


public class Car {

    private String make;
    private String model;
    private int year;

    Car(String make, String model, int year) {
        this.setMake(make);
        this.setModel(model);
        this.setYear(year);
    }

    //getter methods: to change private attribute
    public String getMake(){
        return make;
    }
    public String getModel(){
        return model;
    }
    public int getYear(){
        return year;
    }

    // setter methods:
    public void setMake(String make){
        this.make = make;
    }
    public void setModel(String model){
        this.model = model;
    }
    public void setYear(int year){
        this.year = year;
    }

    // copy method
    public void copy(Car x) {
        this.setModel(x.getModel());
        this.setYear(x.getYear());
        this.setMake(x.getMake());
    }
}
```

can also copy during the creation process of the second car:

```java
public class Main {
    public static void main(String[] args) {

        Car car1 = new Car("Chevrolet", "Camaro", 2021);
        //Car car2 = new Car("Ford", "Mustang", 2022);

        Car car2 = new Car(car1);

        System.out.println(car1);
        System.out.println(car2);
        System.out.println();
        System.out.println(car1.getMake());
        System.out.println(car1.getModel());
        System.out.println(car1.getYear());
        System.out.println();
        System.out.println(car2.getMake());
        System.out.println(car2.getModel());
        System.out.println(car2.getYear());
    }
}



public class Car {

    private String make;
    private String model;
    private int year;

    Car(String make, String model, int year) {
        this.setMake(make);
        this.setModel(model);
        this.setYear(year);
    }

    Car(Car x){
        this.copy(x);
    }

    public String getMake(){
        return make;
    }
    public String getModel(){
        return model;
    }
    public int getYear(){
        return year;
    }

    public void setMake(String make){
        this.make = make;
    }
    public void setModel(String model){
        this.model = model;
    }
    public void setYear(int year){
        this.year = year;
    }

    // copy method
    public void copy(Car x) {
        this.setModel(x.getModel());
        this.setYear(x.getYear());
        this.setMake(x.getMake());
    }
}
```

# interface

a template applied to a class

class can apply more than 1 interface, but only 1 inheritance

```java
public class Main {
    public static void main(String[] args) {

        Rabbit rabbit = new Rabbit();
        rabbit.flee();

        Hawk hawk = new Hawk();
        hawk.hunt();

        Fish fish = new Fish();
        fish.flee();
        fish.hunt();
    }
}



public interface Prey {
    void flee(); // no method body needed
}


public interface Predator {
    void hunt();
}


public class Rabbit implements Prey {

    @Override
    public void flee() {
        System.out.println("The rabbit is fleeing.");
    }
}


public class Hawk implements Predator {
    @Override
    public void hunt() {
        System.out.println("The hawk is hunting.");
    }
}

//Here, Fish class use 2 interface
public class Fish implements Prey, Predator{
    @Override
    public void hunt() {
        System.out.println("This fish is hunting a small fish.");
    }

    @Override
    public void flee() {
        System.out.println("This fish is fleeing from a large fish.");
    }
}
```

# polymorphism

an object been identified as more than one data type.

Here, car, bicycle, boat are both themselves type (car, bicycle and boat) and also a Vehicle type:

```java
public class Main {
    public static void main(String[] args) {

        Car car = new Car();
        Bicycle bicycle = new Bicycle();
        Boat boat = new Boat();

        Vehicle[] racers = {car, bicycle, boat};

        for (Vehicle x : racers) {
            x.go();
        }
    }
}

public class Vehicle {
    public void go(){
        System.out.println("the car is moving.");
    }
}


public class Car extends Vehicle {
    @Override
    public void go(){
        System.out.println("the car is moving.");
    }
}



public class Bicycle extends Vehicle {
    @Override
    public void go(){
        System.out.println("the bicycle is moving.");
    }
}


public class Boat extends Vehicle {
    @Override
    public void go(){
        System.out.println("the boat is moving.");
    }
}
```

# dynamic polymorphism

dynamic: means after the compile (during runtime)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        Animal animal; // create an Animal class but let the user customize the animal type later.

        System.out.println("What animal do you want?");
        System.out.print("1=Cat, 2=Dog: ");
        int choice = scanner.nextInt();

        if(choice==1) {
            animal = new Cat();
            animal.speak();
        }
        else if(choice==2) {
            animal = new Dog();
            animal.speak();
        }
        else {
            animal = new Animal();
            System.out.println("That choice is not correct. ");
            animal.speak();
        }
    }
}


public class Animal {
    public void speak() {
        System.out.println("animal is speaking");
    }
}


public class Cat extends Animal {
    @Override
    public void speak() {
        System.out.println("meow");
    }
}


public class Dog extends Animal {
    @Override
    public void speak() {
        System.out.println("bark");
    }
}
```

# exception

"try catch finally" block

```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        try {
            System.out.println("Enter a whole number: ");
            int x = scanner.nextInt();

            System.out.println("Enter a whole number to be divided: ");
            int y = scanner.nextInt();

            int z = x / y;

            System.out.println("result: " + z);
        } catch (ArithmeticException e) {
            System.out.println("You cannot divide by 0");
        } catch (InputMismatchException e) {
            System.out.println("Please enter a number!");
        } catch (Exception e) {
            System.out.println("Something went wrong");
        } finally {
            System.out.println("this block will always print.");
            scanner.close(); // good practise to close scanner and files at the end.
        }
    }
}
```

# file class

an abstract representation of a file and directory pathnames

```java
import java.io.File;

public class Main {
    public static void main(String[] args) {

        File file = new File("message.txt");

        if(file.exists()) {
            System.out.println("The file exists.");
            System.out.println(file.getPath());
            System.out.println(file.getAbsolutePath());
            System.out.println(file.isFile());
            file.delete();
        }
        else {
            System.out.println("the file does not exists.");
        }
    }
}
```

# FileWriter

```java
import java.io.FileWriter;
import java.io.IOException;

public class Main {
    public static void main(String[] args) {

        try {
            FileWriter writer = new FileWriter("poem.txt");
            writer.write("Roses are red.\nhappy days");
            writer.append("\nbirds are singing");
            writer.close();
        } catch (IOException e) {
            throw new RuntimeException(e);
        }

    }
}
```

# FileReader

read the contents of a file as a stream of characters. read() returns int value contains byte value. When read() returns -1, there is no more data to be read.

```java
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

public class Main {
    public static void main(String[] args) {

        try {
            FileReader reader = new FileReader("poem.txt");
            int data = reader.read();

            while (data != -1) {
                System.out.print((char)data); //cast into character
                data = reader.read();
            }
            reader.close();
        } catch (IOException e) {
            throw new RuntimeException(e);
        }

    }
}
```

# audio

create a audio player in console

```java
import javax.sound.sampled.*;
import java.io.File;
import java.io.IOException;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) throws UnsupportedAudioFileException, IOException, LineUnavailableException {
        Scanner scanner = new Scanner(System.in);

        File file = new File("BabyElephantWalk60.wav");
        AudioInputStream audioStream = AudioSystem.getAudioInputStream(file);
        Clip clip = AudioSystem.getClip();
        clip.open(audioStream);

        String response = "";

        while (!response.equals("Q")) {
            System.out.println("Enter P for play, S for Stop, R for reset, Q for quit.");
            System.out.print("Enter you choice: ");
            response = scanner.next().toUpperCase();

            switch (response) {
                case ("P"):
                    clip.start();
                    break;
                case ("S"):
                    clip.stop();
                    break;
                case ("R"):
                    clip.setMicrosecondPosition(0);
                    break;
                case ("Q"):
                    clip.close();
                    break;
                default:
                    System.out.println("Not a valid response.");
            }
        }
        System.out.println("Bye!");
    }
}
```

# GUI

JFrame: a GUI window to add components

```java
import javax.swing.*;
import java.awt.*;

public class Main {
    public static void main(String[] args) {
        JFrame frame = new JFrame(); //create a frame
        frame.setTitle("Try the frame");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); // make sure to kill the frame, not just hide it to the background
        frame.setSize(420, 420); // set the size
        frame.setResizable(false); // prevent the frame been resized :)
        frame.setVisible(true); // make the frame visible

        ImageIcon image = new ImageIcon("logo.png");
        frame.setIconImage(image.getImage()); // change the frame icon
        frame.getContentPane().setBackground(new Color(205, 55,122)); // change frame background color
    }
}
```

# label

a GUI display area for a string of text, an image, or both.

```java
import javax.swing.*;
import javax.swing.border.Border;
import java.awt.*;

public class Main {
    public static void main(String[] args) {
        ImageIcon image = new ImageIcon("logo.png");

        Border border = BorderFactory.createLineBorder(Color.green, 3);

        JLabel label = new JLabel();
        label.setText("do you code?");
        label.setIcon(image);
        label.setHorizontalTextPosition(JLabel.CENTER); // change the label position center, left or right of the image.
        label.setVerticalTextPosition(JLabel.TOP); // change the vertical position
        label.setForeground(Color.green); // set text font color
        label.setFont(new Font("MV Boli", Font.PLAIN,20)); // set text font
        label.setIconTextGap(-25); // set gap of text to the image
        label.setBackground(Color.black); // set text background color
        label.setOpaque(true); //display background color
        label.setBorder(border); //set label border
        label.setVerticalAlignment(JLabel.CENTER); // set vertical position of icon + text within label
        label.setHorizontalAlignment(JLabel.CENTER);
//        label.setBounds(0,0,250,250);

        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
//        frame.setSize(500, 500);
//        frame.setLayout(null);
        frame.setVisible(true);
        frame.add(label);
        frame.pack(); //adjust the size of the label with the frame
    }
}
```

# panel

a GUI component that functions as a container to hold other components

```java
import javax.swing.*;
import java.awt.*;

public class Main {
    public static void main(String[] args) {

        ImageIcon icon = new ImageIcon("logo.png");
        JLabel label = new JLabel();
        label.setText("Hello");
        label.setIcon(icon);
        label.setVerticalAlignment(JLabel.TOP);
        label.setHorizontalAlignment(JLabel.RIGHT);

        JPanel redPanel = new JPanel();
        redPanel.setBackground(Color.red);
        redPanel.setBounds(0,0,250,250);

        JPanel bluePanel = new JPanel();
        bluePanel.setBackground(Color.blue);
        bluePanel.setBounds(250,0,250,250);

        JPanel greenPanel = new JPanel();
        greenPanel.setBackground(Color.green);
        greenPanel.setBounds(0,250,500,250);
        greenPanel.setLayout(new BorderLayout());

        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(null);
        frame.setSize(750,750);
        frame.setVisible(true);
        redPanel.add(label);
        frame.add(redPanel);
        frame.add(bluePanel);
        frame.add(greenPanel);
    }
}
```

# JButton

a java GUI button

```java
import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class MyFrame extends JFrame {
    JButton button;

    MyFrame(){
        button = new JButton();
        button.setBounds(200,100,100,50);
        button.addActionListener(e -> System.out.println("hello"));

        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setLayout(null);
        this.setSize(500,500);
        this.setVisible(true);
        this.add(button);
    }
}
```
