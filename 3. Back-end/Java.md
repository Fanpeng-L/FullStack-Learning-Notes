<img src="../images/Back-end/JavaCompile.png" width=800 />

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
