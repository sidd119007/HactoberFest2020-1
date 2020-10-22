import csv
student_fields = ['StudentID', 'FirstName', 'LastName', 'Major', 'Phone', 'GPA', 'DOB']
studentDb = 'students.csv'

def display_menu():
    print("1. Add New Student")
    print("2. View Students")
    print("3. Search Student")
    print("4. Quit")


def add_student():
    print("--- Add Student Information ---")

    student_data = []
    for field in student_fields:
        value = input("Enter " + field + ": ")
        student_data.append(value)

    with open(studentDb, "a") as f:
        writer = csv.writer(f)
        writer.writerows([student_data])

    print("Student data saved")
    input("Press any key to continue")
    return


def view_students():
    print("--- Student Records ---")
    with open(studentDb, "r") as f:
        reader = csv.reader(f)
        for x in student_fields:
            print(x, end='\t |')
        print("\n")

        for row in reader:
            for item in row:
                print(item, end='\t |')
            print("\n")

    input("Press any key to continue")

def calculate_gpa():
    with open(studentDb, "r") as f:
        reader = csv.reader(f)
        gpa = 0
        counter = 0
        for row in reader:
            counter = counter + 1
            gpa = gpa + float(row[5])
        return gpa/counter
  

def search_student():
    roll = input("--- Enter Student ID to search --- ")
    avg_gpa = calculate_gpa()
    with open(studentDb, "r") as f:
        reader = csv.reader(f)
        for row in reader:
            if len(row) > 0:
                if roll == row[0]:
                    print("---Student Found ---")
                    print("Student ID: ", row[0])
                    print("First Name: ", row[1])
                    print("Last Name: ", row[2])
                    print("Major: ", row[3])
                    print("Phone: ", row[4])
                    print("GPA: ", row[5])
                    print("DOB: ", row[6])
                    print("Avg GPA:", "{:.2f}".format(avg_gpa))
                    break
        else:
            print("Student ID not found ")
    input("Press any key to continue")

while True:
    display_menu()

    choice = input("Enter your choice: ")
    if choice == '1':
        add_student()
    elif choice == '2':
        view_students()
    elif choice == '3':
        search_student()
    else:
        break

print("Closing...")
