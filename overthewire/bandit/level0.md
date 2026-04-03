# Level 0

The goal of this level is to log into the game using SSH. The host we need to connect to is `bandit.labs.overthewire.org`, on port `2220`. The username is `bandit0` and the password is `bandit0`.

Once logged in, we must go to the `Level 1` page to find out have to beat `Level 1`.

We will being using the command `ssh` and researching over such command and how to acheive our goal.

### Sources Provided

- `https://en.wikipedia.org/wiki/Secure_Shell`
- `https://itsfoss.com/ssh-to-port/`
- `https://www.wikihow.com/Use-SSH`

#### Wikipedia Source

The Secure Shell Protocol is a cryptographic network protocol for operting network services securely over and unsecured network.

SSH uses public-key cryptography to authenticate the remote computer and allow it to authenticate the user, if necessary.

In the simplest form, both ends of a communication channel use automatically generated public-private key pairs to encrypt a network connection, and then use a password to authenticate the user.

When a public-private key pair is made manually, the authentication is performed when the key pair is created, and a sessionmay then open automaticlly without a password prompt. In this case, the public key is placed on all computers that must be allowed access to the owner of the matching private key, which the owner keeps private. The key is never transferred through network and only verifies that the same public key also matches the private key.

#### ItsFoss Source

Learn how to connect via SSH to a port other than the default 22 and how to change the SSH server port.


When we use `ssh user@IP`, it tries to connect to the default port 22. If the remote server uses some other port for SSH, you should provide the port number.

`ssh -p port_number user@IP`

Lets say we wanted to connect to a remote server with an IP of 64.227.184.93 that accepts SSH connections at port 7770.

`ssh -p 7770 abhishek@64.227.184.93`

The process to change the default SSH port on a Linux sever is:
1. Decide our port number
2. If there is a firefall on the server, we must allow the new port
3. We must edit the `/etc/ssh/sshd_config` file and replace the line `#Port 22` with our port number
4. We then restart the SSH service with `systemctl restart sshd`

##### Step 1 (Continued)

We can choose any port number between 0 and 65535 excpet common networking ports such as 21, 80, 443, etc.

In our case, we will being picking port `2220` to progress torward our goal. With previous knowledge, the command we will be using will look like this:

`ssh -p 2220 bandit0@bandit.labs.overthewire.org`


##### Step 2 (Continued)

While I don't think this step is as important for our goal, I will still cover it for some basic knowledge.

We must check the firewall status using the command:

`sudo ufw status`

If active, allow the port using the command:

`sudo ufw allow 2220`

##### Step 3 (Continued)

Again, this probably isn't as important but nonetheless I will cover it.

We will vim or nano the file used to configure our sshd using the command

`nano /etc/ssh/sshd_config`

In the file, we must locate the `#Port 22` line and replace the 22 with our port number and save our changes.

##### Step 4 (Continued)

Restart the ssh daemon using the command:

`systemctl restart sshd`

#### WikiHow: How to use SSH

On windows, users must install an SSH client program (A popular one is Cygwin) and during the installation choose to install OpenSSH. Since linux and Mac OS derived from UNIX, they already come with SSH installed on the system.

We must now run SSH using the terminal and test the connection using the command:

`ssh -p <port> <username>@<remote>`

I will stop here since the site goes more in depth with keys and commands which we don't need yet for level0.

