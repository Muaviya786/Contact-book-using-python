# Contact-book-using-python
# Contact book using the dictionary where user can add, delete and view contacts

contact_book = {}


def add_contact(name, phone_number):
    """Add a new contact to the contact book."""
    if name in contact_book:
        print(f"Contact '{name}' already exists.")
    else:
        contact_book[name] = phone_number
        print(f"Contact '{name}' added successfully.")


def delete_contact(name):
    if name in contact_book:
        del contact_book[name]
        print(f"Contact '{name}' deleted successfully.")
    else:
        print(f"Contact '{name}' not found.")


def view_contacts():
    if contact_book:
        print("Contacts:")
        for name, phone_number in contact_book.items():
            print(f"{name}: {phone_number}")
    else:
        print("No contacts found.")


def main():
    while True:
        print("\nContact Book Menu")
        print("1. Add Contact")
        print("2. Delete Contact")
        print("3. View Contacts")
        print("4. Exit")

        choice = input("Enter your choice (1/2/3/4): ")

        if choice == '1':
            name = input("Enter contact name: ")
            phone_number = input("Enter phone number: ")
            add_contact(name, phone_number)
        elif choice == '2':
            name = input("Enter contact name to delete: ")
            delete_contact(name)
        elif choice == '3':
            view_contacts()
        elif choice == '4':
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 4.")


main()
