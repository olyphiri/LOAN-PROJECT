# LOAN-PROJECT

# Online Python - IDE, Editor, Compiler, Interpreter

def sum(a, b):
    return (a + b)

a = int(input('Enter 1st number: '))
b = int(input('Enter 2nd number: '))

print(f'Sum of {a} and {b} is {sum(a, b)}')
def add_loan(loans):
    loan_id = input("Enter loan ID: ")
    borrower_name = input("Enter borrower name: ")
    loan_amount = float(input("Enter loan amount: "))
    loan_term = int(input("Enter loan term (in months): "))
    loan = {
        "loan_id": loan_id,
        "borrower_name": borrower_name,
        "loan_amount": loan_amount,
        "loan_term": loan_term,
    }
    loans.append(loan)
    print("Loan added successfully.")

def list_loans(loans):
    if not loans:
        print("No loans found.")
        return
    for loan in loans:
        print(loan)

def search_loan(loans):
    loan_id = input("Enter loan ID to search: ")
    for loan in loans:
        if loan["loan_id"] == loan_id:
            print(loan)
            return
    print("Loan not found.")

def update_loan(loans):
    loan_id = input("Enter loan ID to update: ")
    for loan in loans:
        if loan["loan_id"] == loan_id:
            print("Current loan details:")
            print(loan)
            loan["borrower_name"] = input("Enter new borrower name (or press Enter to keep current): ") or loan["borrower_name"]
            loan["loan_amount"] = float(input("Enter new loan amount (or press Enter to keep current): ") or loan["loan_amount"])
            loan["loan_term"] = int(input("Enter new loan term (in months) (or press Enter to keep current): ") or loan["loan_term"])
            print("Loan updated successfully.")
            return
    print("Loan not found.")

def delete_loan(loans):
    loan_id = input("Enter loan ID to delete: ")
    for loan in loans:
        if loan["loan_id"] == loan_id:
            loans.remove(loan)
            print("Loan deleted successfully.")
            return
    print("Loan not found.")

def main():
    loans = []
    while True:
        print("\nLoan Management System")
        print("1. Add Loan")
        print("2. List Loans")
        print("3. Search Loan")
        print("4. Update Loan")
        print("5. Delete Loan")
        print("6. Exit")
        choice = input("Enter your choice: ")
        if choice == "1":
            add_loan(loans)
        elif choice == "2":
            list_loans(loans)
        elif choice == "3":
            search_loan(loans)
        elif choice == "4":
            update_loan(loans)
        elif choice == "5":
            delete_loan(loans)
        elif choice == "6":
            print("Exiting...")
            break
        else:
            print("Invalid choice.")

if __name__ == "__main__":
    main()
