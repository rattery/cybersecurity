# Level 9

The goal is to find the password is stored in the file `data.txt`, being the only line of text that occurs only once.

Knowing that the line occurs only once, we would refer to the `uniq` command which isolates these types of lines once sorted. The command used looks like this:

`sort data.txt | uniq -u`

It sorts the data based on similar text and then provides us with only the `uniq` chracter due to the arg `-u`.

Logged in as bandit 9, found the password in `data.txt`. Moving on to level 10.
Password:4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
