# Level 6 

The goal is to find the password stored in a file under the `inhere` directory which has the properties:
- human-readable
- 1033 bytes in size
- non executable

Using the command:

`find -readable -1033c`

We are able to check if it is human readable and 1033 bytes, which nets use our password.

Logged in as bandit 6, found file `./maybehere07/.file2` and got the password. Moving on to level 7.
