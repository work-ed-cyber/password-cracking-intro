# Introduction to Password Cracking

## Password Attacks

A password attack is just as one would think. The main purpose of these types of attacks is to gain a victim’s password in order to have their credentials and login as that victim. Passwords are meant to authenticate a user on a system, but this can get compromised if a malicious person is able to figure out a person’s password.

## Storing Passwords

Passwords should never be stored in plaintext. For example: A plaintext/unencrypted password could be **p@ssw0rd1@3$5^**.
Windows will hash this password and store it as: **4578A81E395F749BBA1D41B320F8AFFA**.
Linux will hash this password and store it as: **542F3706AF4A262E59A8161D7F4ED679E671E7AB2CA5B49F08308651AC9E0822E544C30C072B60FC204EAEAC118C7A875F90BBD2435CB9982D1F93AFC2F54061**.

## Dictionary Attacks

Dictionary Attacks are a form of a brute force attack that uses commonly used words/passwords from a list. Wordlists are available of cracked/leaked password files from old cyberattacks. Dictionary attacks are only good against simplistic and weak passwords. To combat dictionary attacks, enforce strong password criteria (complexity, length, re-use, etc.).

## Create the Dictionary

- Open Terminal in Kali 
- Navigate to the desktop with the following command: 
````
cd Desktop
````
- Create a .txt file that will serve as the dictionary with the following command: 
````
touch dictionary.txt
````
- Open the dictionary in the nano text editor with the following command: 
````
nano dictionary.txt
````
- In the text editor, type a list of 10 animals. 
- Once finished, press CTRL+X to exit. 
- Press Y to save when prompted.
- Press ENTER to save as the same name (dictionary.txt)

## Create some users

- Login as the root user with the following command:
````
sudo su -
````
- Create additional users by using the following command:
````
useradd mark
````
- This command creates a user with the name 'Mark'
- Create at least 3 users using this command. 
- Remember the users' names - you will need to set passwords for them. 

## Set Passwords
- Use the following command to set a password for each account: 
````
passwd mark
````
- Enter the password at the prompt "Enter new UNIX password."
- Set the password to be one from the list of animals you added to the dictionary file earlier. 
- Repeat this step for all user accounts you created. 

## Locate Hashed Passwords

- Navigate to the etc directory:
````
cd /etc
````
- The file **passwd** contains all the usernames on the system (See the accounts you created?)
- In older systems, the password for each user was stored in the **passwd** file (that's why it's named that)
- Linux switched over to hashing passwords and storing them in a file named **shadow**
- Use the following command to see the hashed passwords in the **shadow** file:
````
cat shadow
````
- Copy the **shadow** file to your Desktop using the following command: 
````
cp shadow /home/kali/Desktop
````

## Launch the Attack

- Navigate to the Desktop directory with the following command:
````
cd /home/kali/Desktop
````
- To launch the attack with the dictionary you created, use the following command:
````
 john shadow --wordlist=dictionary.txt
````
- You should notice John The Ripper cracked the passwords very quickly using the dictionary that you created.

- Please Note: If you see the following message, try the command (all one line).
````
john shadow --wordlist=dictionary.txt –-format=crypt
````
## Real Dictionaries

Real dictionary attacks use millions and billions of passwords. The dictionary file sizes are enormous because of all the possible combinations they contain. Where do these passwords come from? When a cyberattack occurs, the culprits will sometimes leak usernames and passwords online. These are added into a continuously growing list of known passwords and circulated online. A simple Google search will provide plenty of examples that can be used.



