# Algorithm for File Updates in Python

## Project Description
As a security professional, I regularly update a file that identifies employees 
authorized to access restricted content. The file `allow_list.txt` contains 
permitted IP addresses, and a separate `remove_list` identifies IPs that should 
lose access. I created a Python algorithm to automate the process of reading 
the allow list, removing unauthorized IPs, and rewriting the updated file.

---

## Algorithm Walkthrough

### Step 1: Open the File That Contains the Allow List

```python
# Assign `import_file` to the name of the file
import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses no longer allowed access
remove_list = ["192.168.97.225", "192.168.158.170", 
               "192.168.201.40", "192.168.58.57"]

print(import_file)
print(remove_list)
```

`import_file` holds the filename of the allow list. `remove_list` holds the 
IP addresses that need to be revoked. Both are printed to verify the values.

---

### Step 2: Read the File Contents

```python
with open(import_file, "r") as file:
    ip_addresses = file.read()

print(ip_addresses)
```

The `with` statement opens the file and automatically handles closing it. 
The `"r"` parameter opens the file in read mode. The full contents are stored 
as a string in `ip_addresses`.

---

### Step 3: Convert the String into a List

```python
ip_addresses = ip_addresses.split()

print(ip_addresses)
```

The `.split()` method splits the string on whitespace, converting it into a 
Python list where each element is one IP address. This makes it possible to 
iterate and compare individual entries.

---

### Step 4: Iterate Through the Remove List

```python
for element in ip_addresses:
    print(element)
```

A `for` loop iterates through each IP address in the list, making each one 
available for evaluation in the next step.

---

### Step 5: Remove IP Addresses That Are on the Remove List

```python
for element in ip_addresses:
    if element in remove_list:
        ip_addresses.remove(element)

print(ip_addresses)
```

Inside the loop, an `if` statement checks whether the current element exists 
in `remove_list`. If it does, `.remove()` deletes it from `ip_addresses`. 
This ensures all unauthorized IPs are purged from the allow list.

---

### Step 6: Update the File with the Revised List

```python
ip_addresses = " ".join(ip_addresses)

with open(import_file, "w") as file:
    file.write(ip_addresses)
```

`.join()` converts the list back into a single string with spaces between 
each IP. The `with` statement then opens the file in write mode (`"w"`) and 
overwrites it with the updated, cleaned list using `.write()`.

---

## Summary
Built a Python algorithm that opens `allow_list.txt`, reads and converts its 
contents into a list, iterates through the list to remove any IP addresses 
present in the `remove_list`, then rewrites the file with the updated 
authorized IPs. This automates access control maintenance and reduces the 
risk of unauthorized access to restricted resources.

---

**Tools used:** Python 3  
**Skills demonstrated:** File handling, string methods, list iteration, 
conditional logic, access control automation
