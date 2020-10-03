# Enabling password login to the RedHat/Amazon Linux Serve:

1. First we want to generate a new password for the  ec2-user. To generate use following command. (After running below command, type 2 times password which you want to use)
    ```sh
    sudo passwd ec2-user
    ```
2. Update the `PasswordAuthentication` option in the `/etc/ssh/sshd_config` file: `passwordAuthentication yes` (By default it is disabled(`no`), now we need to enable(`yes`))
3. Restart the SSH service by using the following command
    ```sh
    sudo service sshd restart
    ```
4. Now we can able to login via password
    ```sh
    ssh ec2-user@public-ip/public-dns
    ```
5. In feature if we want to remove the password for ec2-user use following command
    ```sh
    sudo passwd -d ec2-user
    ```
6. After we need to update the option `PasswordAuthentication` to `no` in `/etc/ssh/sshd_config` file and restart the `sshd` service.
    ```sh
    sudo service sshd restart
    ```

Note: Password authentication is not more secure than private key authentication, so maximum cases avoid this.
