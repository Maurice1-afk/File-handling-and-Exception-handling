# File-handling-and-Exception-handling
def process_file(input_filename, output_filename):
    try:
        # Try to open and read the input file
        with open(input_filename, "r") as infile:
            content = infile.read()
        
        # Modify content (for example: convert to uppercase)
        modified_content = content.upper()
        
        # Write modified content to output file
        with open(output_filename, "w") as outfile:
            outfile.write(modified_content)
        
        print(f"✅ Successfully created '{output_filename}' with modified content.")

    except FileNotFoundError:
        print(f"❌ Error: The file '{input_filename}' does not exist.")
    except PermissionError:
        print(f"❌ Error: Permission denied when accessing '{input_filename}'.")
    except Exception as e:
        print(f"❌ An unexpected error occurred: {e}")

# Main program
input_file = input("Enter the name of the file to read: ")
output_file = "modified_" + input_file

process_file(input_file, output_file)
