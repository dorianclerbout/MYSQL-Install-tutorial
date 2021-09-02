# Mariadb Install & config

- [1 - Install MariaDB](#1---Install-MariaDB)
- [2 - Secure Database server](#2---Secure-Database-server)



## 1 - Install MariaDB

1. Update your os : 

        sudo apt update && sudo apt -y upgrade

2. Install MariaDB database servers

        sudo apt -y install mariadb-server mariadb-client

3. comfirm version MariaDB installed : 

        apt policy mariadb-server

4. Check server status :

        systemctl status mariadb

## 2 - Secure Database server
    
- Setting strong root password
- Removing anonymous users
- Disabling remote login for root user.
 - Removing test database and access to it

 1.Run the command below to secure your database server

    sudo mysql_secure_installation

    > NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
        >SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

    In order to log into MariaDB to secure it, we'll need the current
    password for the root user. If you've just installed MariaDB, and
    haven't set the root password yet, you should just press enter here.

    Enter current password for root (enter for none): 
    OK, successfully used password, moving on...

    Setting the root password or using the unix_socket ensures that nobody
    can log into the MariaDB root user without the proper authorisation.

    You already have your root account protected, so you can safely answer 'n'.

    Switch to unix_socket authentication [Y/n] n
    ... skipping.

    You already have your root account protected, so you can safely answer 'n'.

    Change the root password? [Y/n] y
    New password: 
    Re-enter new password: 
    Password updated successfully!
    Reloading privilege tables..
    ... Success!


    By default, a MariaDB installation has an anonymous user, allowing anyone
    to log into MariaDB without having to have a user account created for
    them.  This is intended only for testing, and to make the installation
    go a bit smoother.  You should remove them before moving into a
    production environment.

    Remove anonymous users? [Y/n] y
    ... Success!

    Normally, root should only be allowed to connect from 'localhost'.  This
    ensures that someone cannot guess at the root password from the network.

    Disallow root login remotely? [Y/n] y
    ... Success!

    By default, MariaDB comes with a database named 'test' that anyone can
    access.  This is also intended only for testing, and should be removed
    before moving into a production environment.

    Remove test database and access to it? [Y/n] y
    - Dropping test database...
    ... Success!
    - Removing privileges on test database...
    ... Success!

    Reloading the privilege tables will ensure that all changes made so far
    will take effect immediately.

    Reload privilege tables now? [Y/n] y
    ... Success!

    Cleaning up...

    All done!  If you've completed all of the above steps, your MariaDB
    installation should now be secure.

    Thanks for using MariaDB!

2. test installation

        mysql -u root -p