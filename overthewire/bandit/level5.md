# Level 5

The goal is to find the password stored in the only human-readable file in the `inhere` directory.

To find the only human-readable file we must find out the filetypes using the command:

`file ./-*`

This way, we will be presented with one file being ASCII text rather than data, which we will open using the command:

`cat ./-file07`

Logged in as bandit 5, found the `-file07` to be readable and contains the password.
Password:4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
   
