Here’s a **professional GitHub repository post preview (README.md style)** for the Student Information System project based on your code:

---

# Student Information System (C Program)

This is a simple **Student Information System** implemented in C using **structures**. The program allows users to add, display, and manage basic student details such as **Roll Number, Name, and Marks**.

---

## Features

* Add a student with roll number, name, and marks
* Display student information
* Simple menu-driven interface
* Uses **C structures** for data storage

---

## Code Overview

```c
#include <string.h>
struct Student {
    int roll_no;
    char name[50];
    float marks;
};

void addStudent(struct Student *s) {
    printf("Enter Roll Number: ");
    scanf("%d", &s->roll_no);
    getchar(); // Consume newline
    printf("Enter Name: ");
    fgets(s->name, sizeof(s->name), stdin);
    s->name[strcspn(s->name, "\n")] = 0; // Remove trailing newline
    printf("Enter Marks: ");
    scanf("%f", &s->marks);
}

void displayStudent(struct Student s) {
    printf("\nStudent Information:\n");
    printf("Roll Number: %d\n", s.roll_no);
    printf("Name: %s\n", s.name);
    printf("Marks: %.2f\n", s.marks);
}

int main() {
    struct Student student;
    int choice;
    while (1) {
        printf("\nStudent Information System\n");
        printf("1. Add Student\n");
        printf("2. Display Student\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch(choice) {
            case 1: addStudent(&student); break;
            case 2: displayStudent(student); break;
            case 3: printf("Exiting...\n"); return 0;
            default: printf("Invalid choice! Please try again.\n");
        }
    }
    return 0;
}
```

---

## Sample Input/Output

```
Student Information System
1. Add Student
2. Display Student
3. Exit
Enter your choice: 1
Enter Roll Number: 101
Enter Name: John Doe
Enter Marks: 89.5

Student Information System
1. Add Student
2. Display Student
3. Exit
Enter your choice: 2

Student Information:
Roll Number: 101
Name: John Doe
Marks: 89.50

Student Information System
1. Add Student
2. Display Student
3. Exit
Enter your choice: 3
Exiting...
```

---

## How to Run

1. Save the code in a file named `student_info.c`.
2. Compile the program:

   ```bash
   gcc student_info.c -o student_info
   ```
3. Run the program:

   ```bash
   ./student_info
   ```

---

## Future Enhancements

* Add multiple student records
* Include search and delete features
* Store data in a file for persistence

---

