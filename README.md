# This work done by group 6:
# Manal Khalid, 202283500, 50%
# Rand Turki, 202253680, 50%



###
#Employee Information System...
#aim of the project: to write a software code to store employee information in a text file for certain company...
##



def get_employees_information():
# to collect employee data based on Table 1 specs.s provided in project description
    while True:
        try:
            employee_id = int(input("Enter employee ID (1 to 5 digits): "))
            if 1 <= len(str(employee_id)) <= 5:
                break
            else:
                print("Invalid ID number, please enter a 1 to 5-digit ID")
        except ValueError:
            print("Invalid input. Please enter a numeric value.")
    employee_name = str(input("Enter employee  name (First name, Last name):"))
    employee_department = str(input('Enter a department: '))
    employee_job_title = str(input('Enter the job title: '))       
    employee_email =str(input('Enter the email: '))
    
    while True:
        try:
            employee_salary = float(input("Enter the salart ($1500-$10,000):"))
            if employee_salary<=10000 and employee_salary>=1500:
                raise ValueError
            break
        except ValueError:
            print("Invalid salary value, please enter a salary between $1500 to $10000")
            
    while True:
        try:
            employee_phone = int(input('Enter phone number (10 numbers starting with 05): ')) 
            if not (len(str(employee_phone))==10 and str(employee_phone).startwith("05")):
                raise ValueErrorr
            break
        except ValueError:
            print("Invalid phone number, please enter a phone number that starts with 05 and contains only 10 digits")
            
    return {"id":employee_id,"name": ,"department":employee_department,"job_title":employee_job_title,"salary":employee_salary,"email":employee_email}

##########################
def add_employee(employees): #new function by manal, a qick so I can remmember new function I add... 
    employee = get_employees_information()
    file.write(get_employees_information(employee) + "\n")
    print("new employee added to the file successfully.")
    

    

    
def remove_employee(employees):
    # For the user to enter the ID of the employee to remove
    employee_id = int(input("Enter employee ID to remove: "))

    # Check if the employee with the specified ID exists
    employee_found = False
    for employee in employees:
        if employee.id == employee_id:
            employee_found = True
            break

    # If the employee exists, proceed with removal
    if employee_found:
        # Confirm employee removal with the user
        print(f"Are you sure you want to remove employee with ID {employee_id}?")
        choice = input("Enter your choice (Yes/No): ").upper()

        if choice == "Yes":
            # Remove the employee from the list
            employees.remove(employee)
            print(f"Employee with ID {employee_id} removed successfully.")
        else:
            print("Employee removal canceled.")
    else:
        print(f"Employee with ID {employee_id} not found.")

    

def modify_employee_information():
    # to modify specific information of an employee
    

def display_employee_information(employees):
    # to display employee information based on user criteria
    print("Select display option:") 
    print("1. Display all employees' information") 
    print("2. Display all employees' information sorted by salary (ascending order)") 
    print("3. Display all employees' information sorted by salary (descending order)") 
    print("4. Display specific employee information based on ID") 
    choice = int(input("Enter your choice: "))

def save_to_file(employees):
    # to save employee information to a file
    open("employees system information.txt","w")
    employee = get_employees_information()
    file.write(get_employees_information(employee) + "\n")
    print("new employee added to the file successfully.")
    close("employees system information.txt")
    
    

def load_from_file():
    # to load employee information from a file
    

def main():
    employees = load_from_file()

    while True:
        # Display menu
        print("\nCompany XYZ Employee’s Information System")
        print("1. Add an employee to the company.")
        print("2. Remove an employee from the company.")
        print("3. Modify an employee’s information.")
        print("4. Display the information of a specific employee.")
        print("5. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            add_employee()
        elif choice == "2":
            remove_employee()
        elif choice == "3":
            modify_employee_information()
        elif choice == "4":
            display_employee_information()
        elif choice == "5":
            save_to_file(employees)
            print("Exiting the program. Goodbye!")
            break
        else:
            print("Invalid choice. Please choose again.")

if __name__ == "__main__":
    main()
