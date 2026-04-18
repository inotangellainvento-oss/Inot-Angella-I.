def main():
    filename = "notes.txt"

    try:
        message = input("Enter a short note/message: ")
        with open(filename, "w") as file:
            file.write(message + "\n")
        print(f"Message successfully saved to {filename}.\n")

    
        print("--- Reading File Content ---")
        with open(filename, "r") as file:
            content = file.read()
            print("Content:", content)

    
        new_note = input("Enter another note to append: ")
        with open(filename, "a") as file:
            file.write(new_note + "\n")
        
        print("\n--- Displaying Updated Content ---")
        with open(filename, "r") as file:
            updated_content = file.read()
            print(updated_content)

    except FileNotFoundError:
        print("Error: The file was not found.")
    except PermissionError:
        print("Error: You do not have permission to access this file.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

if __name__ == "__main__":
    main()
