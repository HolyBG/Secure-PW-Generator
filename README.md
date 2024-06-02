# Secure Password Generator

## Objective

This secure password generator was created using Python. It will take input from the user then create a password that could contain uppercase, lowercase, numbers, and symbols. Bitwarden, a widely used password manager, recommends password lengths of at least fourteen characters. I used this as the baseline for my project. This coding project helped to re-enforce python coding fundamentals and introduced me to some key concepts. 

### Skills Learned

- Functions from the Random module
- Functions from the String module
- Secure Password Practices
- Creating functions

### Tools Used

- VSCode
- Python 3.12

## Steps
Here is the code that I created within VSCode:
```
import random
import string

def generate_password(length: int): #creates a functions with a length parameter. The arguement needs to be an int.
    ascii_table = string.ascii_letters + string.digits + string.punctuation #builds a string that contains upper & lowercase letters, numbers 0-9, and symbols for the password
    password = "".join(random.choice(ascii_table)
                        for char in range(length))
    return password #creates an empty string that is joined with a for loop that is choosing random characters from the ascii_table variable
    
#################################################
#Welcome Text

print("Welcome to My Simple Password Generator!\n Let me create a secure password for you.")
is_secure = False
while is_secure == False: #while loops checks if the user has picked a character length that is longer than 13.
    pw_length = int(input("\nHow many characters do you want in your password?\n"))
    if pw_length < 14:
        print("\nProtect yourself from hackers!\nChoose a password length that is greater than 13 characters")
    else:
        is_secure = True #breaks question loop when the secure length is reached.

password = generate_password(pw_length)

print(f"\nGenerated Password: {password}")

```

### Example below

User starts the program and is prompted for their desired password length:

![Start](https://github.com/HolyBG/Secure-PW-Generator/assets/111000839/9c89e854-eb1b-41dd-9897-3bb5b9d07a9f)

If the user what to generate a weaker password (any password that is less than 14 charaters) then the script rejects the input and asks the user to enter something more secure:

![Unsecure PW](https://github.com/HolyBG/Secure-PW-Generator/assets/111000839/668f9b5e-6062-4ded-8d10-42d577610e92)

Once the user selects something that is secure the script will generate the password.

![Secure PW](https://github.com/HolyBG/Secure-PW-Generator/assets/111000839/71b475d1-5abc-4b4c-b06c-d8960212c197)

### Future Improvements
The script, at the moment, chooses characters at random from a large string of characters. This is ok, but some websites require a minimum amount of symbols and numbers in an acceptable password. Changes could be made to accommodate this.


