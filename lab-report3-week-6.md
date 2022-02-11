# Lab Report 3 - Streamlining SSH Configuration
[Back](https://bimai25.github.io/cse15l-lab-reports/index.html)
## Creating the SSH Config File
![Image](./screenshots/lab-report-3/config_vscode.png)
The `ssh` process of logging into ieng6 can be streamlined through the command `ssh ieng6`. However, in order ot make this command work, a file named `config` needs to be crated in the `.ssh` directory and filled with the information above.

## SSH Login With New Alias
![Image](./screenshots/lab-report-3/ssh_login.png)
When the `ssh ieng6` terminal command is setup, the user, as defined from the `config` file, is automatically logged in using a one liner. Even with a RSA key setup, the one line command still functions and logs in properly.

## SCP Command Using New Alias
![Image](./screenshots/lab-report-3/scp.png)
`ieng6` can now be used in replacement of `cs15lwi22aas@ieng6.ucsd.edu` for any command. Running `scp hello.txt ieng6:~` will copy the file hello.txt to the user's ieng6 profile without typing out the long username.