filename = input("Enter the filename to read: ")

try:
    # Try to open and read the file
    with open(filename, "r") as infile:
        contents = infile.read()

    # Process content (convert to uppercase + count words)
    word_count = len(contents.split())
    modified_data = contents.upper()

    # Write to output.txt
    with open("output.txt", "w") as outfile:
        outfile.write(modified_data)
        outfile.write(f"\n\nWord Count: {word_count}\n")

    print("✅ Success! File processed and saved as 'output.txt'.")

except FileNotFoundError:
    print("❌ Error: The file does not exist.")
except PermissionError:
    print("❌ Error: You don’t have permission to read this file.")
except Exception as e:
    print(f"⚠️ An unexpected error occurred: {e}")
