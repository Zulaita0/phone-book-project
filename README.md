# phone-book-project
Simple Python phone book CLI project with add, remove, search, and validation features.
print("What do you want to do?")

num = {
    "1111111111": "Amal",
    "2222222222": "Mohammed",
    "3333333333": "khadijah",
    "4444444444": "Abdullah",
    "5555555555": "Rawan",
    "6666666666": "Faisal",
    "7777777777": "Layla"
}


def is_valid_number(number):
    if len(number) != 10:
        return False
    if not number.isdigit():
        return False
    return True


def find_number_by_name():
    name = input("Enter the name: ")

    for number, owner in num.items():
        if owner == name:
            print(number)
            return

    print("Sorry, the name is not found")


while True:
    print("\ncommand: view / add / remove / search / exit")
    command = input("Enter a command or number: ")

    if command == "view":
        print("\nYour numbers are:")

        for number, name in num.items():
            print(f"{number} : {name}")

    elif command in num:
        print(f"Your number is: {num[command]}")

    elif command == "add":
        num_number = input("The number you want to add: ")

        if not is_valid_number(num_number):
            print("This is invalid number")
        else:
            num_name = input("The name you want to add: ")
            num[num_number] = num_name
            print("Added successfully ")

    elif command == "remove":
        num_number = input("The number you want to remove: ")

        if num_number in num:
            del num[num_number]
            print("Removed successfully ✔")
        else:
            print("Number not found")

    elif command == "search":
        find_number_by_name()

    elif command == "exit":
        print("Goodbye ")
        break

    else:
        print("Please enter a valid command")
