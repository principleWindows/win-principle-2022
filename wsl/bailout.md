# Bailout

*************************************

## Index

1. [How to modify the default user of Windows10 WSL](#how-to-modify-the-default-user-of-windows10-wsl)
2. [How to Reset Ubuntu Linux Password on WSL](#how-to-reset-ubuntu-linux-password-on-wsl)


## 1 How to modify the default user of Windows10 WSL

If you were using the Ubuntu app from Windows store, the command would be:

```batch
ubuntu config --default-user root
```

If you were using Ubuntu 20.04, the command would be:

```batch
ubuntu2004 config --default-user root
``` 

For Ubuntu version 18.04£º
```batch
ubuntu1804 config --default-user root
```

[Back to index](#index)


## 2 How to Reset Ubuntu Linux Password on WSL

When you install Linux using WSL on Windows, you are asked to create a username 
and password. This user is automatically logged on when you start Linux on WSL.

Now, the problem is that if you haven¡¯t used it for some time, you may forget 
the account password of WSL. And this will become a problem if you have to use 
a command with sudo because here you¡¯ll need to enter the password.

To reset the Linux password in WSL, you have to:

- Switch the default user to root
- Reset the password for the normal user
- Switch back the default user to the normal user

The root user in WSL is unlocked and doesn¡¯t have a password set. This means 
that you can switch to the root user and then use the power of root to reset 
the password.

Since you don¡¯t remember the account password, switching to the root user 
is done by changing the configuration of your Linux WSL application and make 
it use root user by default.

Do you remember the username in WSL? If not, you can always check the 
contents of the /home directory. When you have the username, use this command:
```batch
passwd username
```

It will ask you to enter a new password. When you type here, nothing will be 
displayed on the screen. That¡¯s normal. Just type the new password and hit 
enter. You¡¯ll have to retype the new password to confirm and once again, 
nothing will be displayed on the screen while you type the password.

**Summerize**

1. Close the current Ubuntu instance
2. Open Powershell and log in to a WSL instance as a particular user by using 
the -u or ¨Cuser flag
```batch
ubuntu -u root
```
or
```batch
ubuntu1804 -u root
```
or
```batch
wsl -u root
```
3. Now in the same Powershell terminal, input `wsl` and type enter
4. to change the password, use the following command:
```batch
passwd username
```
5. exit WSL by typing `exit`

[Back to index](#index)


