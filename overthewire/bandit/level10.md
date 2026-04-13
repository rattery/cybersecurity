# Level 10

The goal of this level is to find the password stored in the `data.txt`, being one of the few human-readable strings, preceded by several ‘=’ characters.

Using cat won't work anymore due to the varying data types. For this reason, we use `strings` to display only the human-readable text while using `grep`. The command ran is:

`strings data.txt | grep ===`

Logged in as bandit10, found the password in `data.txt`. Moving on to level 11.
Password:FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

