# Project

students = []

def add_student():
    student_id = input("Enter Student ID: ")
    name = input("Enter Student Name: ")
    age = input("Enter Age: ")
    course = input("Enter Course: ")

    student = {
        "id": student_id,
        "name": name,
        "age": age,
        "course": course
    }

    students.append(student)
    print("Student added successfully.\n")


def view_students():
    if not students:
        print("No student records found.\n")
        return

    for student in students:
        print("ID:", student["id"])
        print("Name:", student["name"])
        print("Age:", student["age"])
        print("Course:", student["course"])
        print("-" * 20)


def search_student():
    search_id = input("Enter Student ID to search: ")
    for student in students:
        if student["id"] == search_id:
            print("Student Found:")
            print(student)
            return
    print("Student not found.\n")


def delete_student():
    delete_id = input("Enter Student ID to delete: ")
    for student in students:
        if student["id"] == delete_id:
            students.remove(student)
            print("Student record deleted.\n")
            return
    print("Student not found.\n")


while True:
    print("Student Management System")
    print("1. Add Student")
    print("2. View Students")
    print("3. Search Student")
    print("4. Delete Student")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_student()
    elif choice == "2":
        view_students()
    elif choice == "3":
        search_student()
    elif choice == "4":
        delete_student()
    elif choice == "5":
        print("Thank you for using the system.")
        break
    else:
        print("Invalid choice. Try again.\n")
 