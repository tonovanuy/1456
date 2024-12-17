import java.util.HashSet;

class Student {
    String name;
    int age;
    int id;

    // Конструктор
    public Student(String name, int age, int id) {
        this.name = name;
        this.age = age;
        this.id = id;
    }

    // Метод для виведення інформації
    public String toString() {
        return name + " (Age: " + age + ", ID: " + id + ")";
    }
}

public class Main {
    public static void main(String[] args) {
        HashSet<Student> students = new HashSet<>();
        
        students.add(new Student("John", 21, 1001));
        students.add(new Student("Mary", 22, 1002));
        students.add(new Student("Jake", 23, 1003));
        students.add(new Student("Olivia", 20, 1004));
        students.add(new Student("Emma", 24, 1005));

        for (Student student : students) {
            System.out.println(student);
        }
    }
    
}

import java.util.ArrayList;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> items = new ArrayList<>();
        items.add("Apple");
        items.add("Banana");
        items.add("Orange");
        items.add("Grapes");
        items.add("Mango");
        items.add("Peach");
        items.add("Plum");
        items.add("Pineapple");
        items.add("Watermelon");
        items.add("Strawberry");

        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("Меню:");
            System.out.println("1. Додати елемент");
            System.out.println("2. Видалити елемент");
            System.out.println("3. Вихід");
            System.out.print("Ваш вибір: ");
            int choice = scanner.nextInt();
            scanner.nextLine();  // Очищаємо буфер

            if (choice == 1) {
                System.out.print("Введіть елемент для додавання: ");
                String newItem = scanner.nextLine();
                items.add(newItem);
                System.out.println("Елемент додано.");
            } else if (choice == 2) {
                System.out.print("Введіть індекс елемента для видалення: ");
                int index = scanner.nextInt();
                if (index >= 0 && index < items.size()) {
                    items.remove(index);
                    System.out.println("Елемент видалено.");
                } else {
                    System.out.println("Невірний індекс.");
                }
            } else if (choice == 3) {
                break;
            } else {
                System.out.println("Невірний вибір, спробуйте знову.");
            }

            // Виводимо поточний список
            System.out.println("Теперішній список:");
            for (String item : items) {
                System.out.println(item);
            }
        }

        scanner.close();
    }
}

import java.util.ArrayList;
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();
        Random rand = new Random();

        // Заповнюємо колекцію випадковими числами
        for (int i = 0; i < 5; i++) {
            numbers.add(rand.nextInt(50) + 1); // Числа від 1 до 50
        }

        // Виводимо числа
        System.out.println("Числа в колекції:");
        for (int number : numbers) {
            System.out.println(number);
        }

        // Знаходимо максимальне та мінімальне число
        int max = Integer.MIN_VALUE;
        int min = Integer.MAX_VALUE;
        int maxIndex = -1;
        int minIndex = -1;

        for (int i = 0; i < numbers.size(); i++) {
            if (numbers.get(i) > max) {
                max = numbers.get(i);
                maxIndex = i;
            }
            if (numbers.get(i) < min) {
                min = numbers.get(i);
                minIndex = i;
            }
        }

        // Виводимо результат
        System.out.println("Максимальне число: " + max + " (Індекс: " + maxIndex + ")");
        System.out.println("Мінімальне число: " + min + " (Індекс: " + minIndex + ")");
    }
}
