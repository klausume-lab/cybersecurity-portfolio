# Python — Updating an IP Allow List

**Context:** Google Cybersecurity Certificate coursework / simulation.  
**Status:** Documented algorithm; sample-file verification described in validation notes.

## Project description
For this cybersecurity exercise, I worked through a simulated healthcare-company scenario that controls access to restricted information through an approved list of IP addresses. Some employees no longer need access, so their addresses must be taken off the allow list. I developed a Python algorithm that reads the allow_list.txt file, checks it against a separate remove list, and saves the updated list. The purpose is to make access updates more accurate, reduce manual work, and help protect sensitive information.
## Open the file that contains the allow list
I started by assigning the name of the allow list file to a variable called import_file. I also defined remove_list to hold the four IP addresses that must no longer have access. I used the with statement and open() function to open the file in read mode. The "r" argument means read, while "as file" creates a file object that I can work with. Using with also makes sure Python closes the file after I am done reading.


```python
import_file = "allow_list.txt"
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]


with open(import_file, "r") as file:
    ip_addresses = file.read()
```

## Read the file contents
Once the file was open, I used the .read() method to collect its contents. I assigned the result to the variable ip_addresses. This gives me the approved IP addresses as one string, which I can process in the next steps. The .read() method belongs to the file object, so it is written as file.read(). I read the data before making any changes to the allow list.


```python
with open(import_file, "r") as file:
    ip_addresses = file.read()
```

## Convert the string into a list
The contents of ip_addresses start as a string, but I need a list so I can remove individual IP addresses. I used the .split() method to separate the string wherever there is whitespace, including spaces or new lines. The result is a list with one IP address in each element. I stored that list back in ip_addresses so it can be checked and updated.


```python
ip_addresses = ip_addresses.split()
```

## Iterate through the remove list
Next, I used a for loop to go through the IP addresses in remove_list one by one. The keyword for starts the loop, element holds the address being checked, and in identifies the list to inspect. It is important to iterate over remove_list, not over ip_addresses, because the next step changes ip_addresses. This avoids skipping addresses while removing them from the allow list.


```python
for element in remove_list:
    # Check whether this address is still in the allow list
    if element in ip_addresses:
        ip_addresses.remove(element)
```

## Remove IP addresses that are on the remove list
Inside the loop, I used the condition if element in ip_addresses to see whether the current address is still approved. If the condition is true, the .remove() method takes that address out of the list. Checking membership first matters because .remove() raises an error when the value is missing. The exercise states that the allow list has no duplicate addresses, so removing an address once is enough. Looping through remove_list, rather than changing the list I am iterating over, makes this step more reliable.


```python
for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)
```

## Update the file with the revised list of IP addresses
After filtering the list, I needed to save the remaining IP addresses back to the original file. I used the .join() method with a newline separator ("\n") to turn the list into a string with one IP address on each line. Then I opened allow_list.txt again using "w" for write mode and used file.write() to replace the old contents. The with statement closes the file when writing is complete. This updates the allow list so the removed addresses are no longer included. In a real environment, I would also verify the result and keep a backup before overwriting an access-control file.


Here is the complete corrected algorithm, ready to review as one code sample:


```python
import_file = "allow_list.txt"
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]


with open(import_file, "r") as file:
    ip_addresses = file.read()


ip_addresses = ip_addresses.split()


for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)


ip_addresses = "\n".join(ip_addresses)


with open(import_file, "w") as file:
    file.write(ip_addresses)
```

## Summary
I built an algorithm that updates a simulated healthcare company's IP address allow list by removing addresses that no longer have permission to access restricted information. First, the program opens the file, reads its contents, and converts the text into a list. Then it checks each address in remove_list and removes any matching address from the approved list. After that, it joins the remaining addresses into a newline-separated string and writes the updated contents back to allow_list.txt. This exercise helped me practice file handling, lists, loops, conditional statements, and automation with Python. It also showed me why checking for a match before removing an item is important for preventing errors.

## Runnable source and checks

- [Course algorithm](update_allow_list.py)
- [Local verification](verification.md)

Editing a text file alone does not prove a real network enforces that file. This example assumes whitespace-separated entries, unique allow-list addresses, and an existing readable file. It overwrites the target file and is a learning example, not a production access-control service.

## Evidence and attribution

Adapted from the Drive document “Algorithm for file updates in Python”. Source response text and supplied scenario material may coexist in course templates. This portfolio was organized and edited with AI assistance; it does not claim independent authorship of course materials or production security work. See [source register](../../docs/source-register.md).

[Back to portfolio](../../README.md)
