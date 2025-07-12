
import java.util.*;

class Student {
    int id;
    String name;
    boolean isPresent;

    Student(int id, String name) {
        this.id = id;
        this.name = name;
        this.isPresent = false; // Default: absent
    }

    void markPresent() {
        isPresent = true;
    }

    void markAbsent() {
        isPresent = false;
    }

    void displayStatus() {
        System.out.println("ID: " + id + ", Name: " + name + ", Attendance: " + (isPresent ? "Present" : "Absent"));
    }
}

public class AttendanceSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Sample students
        Student[] students = {
            new Student(1, "Alice"),
            new Student(2, "Bob"),
            new Student(3, "Charlie")
        };

        System.out.println("=== Attendance Marking ===");
        for (Student student : students) {
            System.out.print("Is " + student.name + " present? (y/n): ");
            String input = scanner.next();
            if (input.equalsIgnoreCase("y")) {
                student.markPresent();
            } else {
                student.markAbsent();
            }
        }

        System.out.println("\n=== Attendance Report ===");
        for (Student student : students) {
            student.displayStatus();
        }

        scanner.close();
    }
}
