# c-
#include <iostream>
using namespace std;

class Student {
protected:
    int roll_number;
    string name;
    float marks[5];

public:
    // Default Constructor
    Student() {
        roll_number = 0;
        name = "Unknown";
        for(int i = 0; i < 5; i++)
            marks[i] = 0;
    }

    // Parameterized Constructor (Full Info)
    Student(int r, string n, float m[]) {
        roll_number = r;
        name = n;
        for(int i = 0; i < 5; i++)
            marks[i] = m[i];
    }

    // Overloaded Constructor (Only Roll Number)
    Student(int r) {
        roll_number = r;
        name = "Not Assigned";
        for(int i = 0; i < 5; i++)
            marks[i] = 0;
    }

    // Destructor
    ~Student() {
        cout << "Destructor called for Roll No: " << roll_number << endl;
    }

    // Add Student Details
    void addStudent() {
        cout << "Enter Roll Number: ";
        cin >> roll_number;
        cout << "Enter Name: ";
        cin >> name;

        cout << "Enter 5 subject marks:\n";
        for(int i = 0; i < 5; i++) {
            cin >> marks[i];
        }
    }

    // Overloaded addStudent()
    void addStudent(int r, string n) {
        roll_number = r;
        name = n;
    }

    // Modify Student
    void modifyStudent() {
        cout << "Modify Name: ";
        cin >> name;

        cout << "Modify Marks:\n";
        for(int i = 0; i < 5; i++) {
            cin >> marks[i];
        }
    }

    // Display Student
    void displayStudent() {
        cout << "\n--- Student Record ---\n";
        cout << "Roll Number: " << roll_number << endl;
        cout << "Name: " << name << endl;
        cout << "Marks: ";
        for(int i = 0; i < 5; i++) {
            cout << marks[i] << " ";
        }
        cout << endl;
    }

    // Calculate Average
    float calculateAverage() {
        float sum = 0;
        for(int i = 0; i < 5; i++) {
            sum += marks[i];
        }
        return sum / 5;
    }
};
