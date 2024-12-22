# week-4-python-programming

Task 1: File Read & Write Challenge 🖋️


Read content from an existing file.
Modify its content (for example, converting all text to uppercase).
Write the modified content to a new file.
Task 2: Error Handling Lab 🧪


Ask the user for the filename.
If the file doesn't exist or there is an error reading it, provide appropriate error messages.


def read_and_modify_file(input_filename, output_filename):
    try:
        # Open the input file to read
        with open(input_filename, 'r') as file:
            content = file.read()
        
        # Modify the content (e.g., convert to uppercase)
        modified_content = content.upper()

        # Write the modified content to the new output file
        with open(output_filename, 'w') as file:
            file.write(modified_content)
        
        print(f"File has been modified and saved as {output_filename}")
    
    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' was not found.")
    except IOError:
        print(f"Error: Could not read/write the file '{input_filename}' or '{output_filename}'.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

def main():
    # Ask the user for the filename
    input_filename = input("Enter the filename to read: ")
    output_filename = input("Enter the filename to save the modified content: ")

    # Call the function to read, modify, and write the file
    read_and_modify_file(input_filename, output_filename)




Example Run:
Valid case (input file exists):

Enter the filename to read: example.txt
Enter the filename to save the modified content: modified_example.txt
File has been modified and saved as modified_example.txt
Error case (file doesn't exist):
vbnet
Copy code
Enter the filename to read: non_existent_file.txt
Enter the filename to save the modified content: output.txt
Error: The file 'non_existent_file.txt' was not found.
