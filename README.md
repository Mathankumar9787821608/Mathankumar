students = []

def add_student():
    name = input("Enter Student Name: ")
    roll = input("Enter Roll Number: ")
    dept = input("Enter Department: ")
    student = {"Name": name, "Roll": roll, "Dept": dept}
    students.append(student)
    print("✅ Student added successfully!\n")

def view_students():
    if not students:
        print("No students found.\n")
        return
    print("\n--- Student List ---")
    for i, student in enumerate(students, start=1):
        print(f"{i}. {student['Name']} | Roll: {student['Roll']} | Dept: {student['Dept']}")
    print()

def remove_student():
    roll = input("Enter Roll Number to remove: ")
    for student in students:
        if student["Roll"] == roll:
            students.remove(student)
            print("🗑️ Student removed successfully!\n")
            return
    print("❌ Student not found.\n")

def menu():
    while True:
        print("=== Student Management System ===")
        print("1. Add Student")
        print("2. View Students")
        print("3. Remove Student")
        print("4. Exit")
        choice = input("Enter your choice: ")

        if choice == "1":
            add_student()
        elif choice == "2":
            view_students()
        elif choice == "3":
            remove_student()
        elif choice == "4":
            print("👋 Exiting Program...")
            break
        else:
            print("Invalid choice! Try again.\n")

menu()
