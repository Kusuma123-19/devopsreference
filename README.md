## Ansible Setup Commands and Purpose

| **Command**                                                    | **Purpose**                                                                                                                 |
| -------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `useradd -m -s /bin/bash ansible`                              | Creates a new user named **ansible** with a home directory and Bash shell.                                                  |
| `passwd ansible`                                               | Sets a password for the **ansible** user.                                                                                   |
| `visudo`                                                       | Opens the sudoers file to grant sudo privileges to the ansible user.                                                        |
| `vi /etc/ssh/sshd_config`                                      | Opens the SSH configuration file to modify SSH settings.                                                                    |
| `systemctl restart ssh`                                        | Restarts the SSH service to apply the configuration changes.                                                                |
| `su - ansible`                                                 | Switches from the root user to the ansible user.                                                                            |
| `ssh-keygen`                                                   | Generates an SSH public and private key pair.                                                                               |
| `cd .ssh`                                                      | Changes to the `.ssh` directory.                                                                                            |
| `ls`                                                           | Lists the files in the current directory.                                                                                   |
| `cat id_ed25519.pub`                                           | Displays the ED25519 public key.                                                                                            |
| `rm -rf .ssh/*`                                                | Removes all existing SSH keys from the `.ssh` directory.                                                                    |
| `ssh-keygen -t rsa -b 4096 -f /home/ansible/.ssh/id_rsa -N ""` | Generates a 4096-bit RSA key pair without a passphrase.                                                                     |
| `ll`                                                           | Displays a detailed list of files and directories.                                                                          |
| `cat id_rsa.pub`                                               | Displays the RSA public key to copy it to the target server.                                                                |
| `exit`                                                         | Logs out from the current user session.                                                                                     |
| `vi /etc/ansible/hosts`                                        | Opens the Ansible inventory file to add managed hosts.                                                                      |
| `ssh 172.31.31.125`                                            | Connects to the managed node using SSH.                                                                                     |
| `ansible dev -m ping`                                          | Tests connectivity between the Ansible control node and all hosts in the **dev** inventory group using the **ping** module. |

### Output

| **Output**       | **Purpose**                                                                                |
| ---------------- | ------------------------------------------------------------------------------------------ |
| `"ping": "pong"` | Confirms that the Ansible control node can successfully communicate with the managed node. |
| `SUCCESS`        | Indicates that the Ansible command executed successfully on the managed host.              |
## Managed Node (Target Server) - Commands and Purpose

| **Command**                       | **Purpose**                                                                                              |
| --------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `useradd -m -s /bin/bash ansible` | Creates a new user named **ansible** with a home directory and Bash shell.                               |
| `passwd ansible`                  | Sets a password for the **ansible** user.                                                                |
| `visudo`                          | Opens the sudoers file to grant sudo privileges to the ansible user.                                     |
| `vi /etc/ssh/sshd_config`         | Opens the SSH configuration file to configure SSH settings.                                              |
| `systemctl restart ssh`           | Restarts the SSH service to apply the configuration changes.                                             |
| `su - ansible`                    | Switches from the root user to the ansible user.                                                         |
| `ls -a`                           | Lists all files and directories, including hidden files.                                                 |
| `mkdir .ssh`                      | Creates the `.ssh` directory to store SSH-related files.                                                 |
| `ls -l`                           | Displays a detailed list of files and directories.                                                       |
| `ll`                              | Shows a detailed listing with file permissions, owner, size, and date.                                   |
| `chmod 700 .ssh/`                 | Sets the `.ssh` directory permissions so that only the owner can read, write, and execute it.            |
| `cd .ssh/`                        | Changes to the `.ssh` directory.                                                                         |
| `pwd`                             | Displays the current working directory.                                                                  |
| `vi authorized_keys`              | Creates or opens the `authorized_keys` file and pastes the public SSH key from the Ansible control node. |
| `chmod 600 authorized_keys`       | Sets the `authorized_keys` file permissions so only the owner can read and write it.                     |
| `ll`                              | Verifies the permissions of the `.ssh` directory and `authorized_keys` file.                             |
| `exit`                            | Logs out from the ansible user and returns to the root user.                                             |
| `systemctl restart ssh`           | Restarts the SSH service after configuring the SSH keys.                                                 |
