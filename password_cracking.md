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
~~~~
cd Desktop
~~~~
- Create a .txt file that will serve as the dictionary with the following command: 
~~~~
touch dictionary.txt
~~~~
- Open the dictionary in the nano text editor with the following command: 
~~~~
nano dictionary.txt
~~~~

