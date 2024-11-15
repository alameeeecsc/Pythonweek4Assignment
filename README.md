# File Read & Write Challenge and Error Handling Lab

def read_and_modify_file(input_filename, output_filename):
    try:
        # Open the input file in read mode
        with open(input_filename, 'r') as infile:
            # Read the contents of the file
            content = infile.read()
        
        # Modify the content (example: convert to uppercase)
        modified_content = content.upper()

        # Open the output file in write mode
        with open(output_filename, 'w') as outfile:
            # Write the modified content to the new file
            outfile.write(modified_content)

        print(f"File successfully modified and saved as {output_filename}")

    except FileNotFoundError:
        print(f"Error: The file {input_filename} does not exist.")
    except PermissionError:
        print(f"Error: You do not have permission to read or write to the file.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Ask the user for the input and output file names
input_filename = input("Enter the name of the file to read from: ")
output_filename = input("Enter the name of the file to write to: ")

# Call the function to read, modify, and write the file
read_and_modify_file(input_filename, output_filename)
