# -Automation-with-Python-Scripts-
import re

# Define input and output file names
input_file = 'emails.txt'                 
output_file = 'extracted_emails.txt'      

# Open and read the content of the input file
with open(input_file, 'r') as file:
    content = file.read()

# Use regex to find all email addresses
emails = re.findall(r'[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+', content)

# Write the found emails into the output file
with open(output_file, 'w') as file:
    for email in emails:
        file.write(email + '\n')

print(f"✅ {len(emails)} email(s) extracted and saved to '{output_file}'.")
