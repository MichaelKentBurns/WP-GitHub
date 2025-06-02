# WP-Github - bash edition

## Assumptions:
    * Your WordPress instance is hosted on a Linux based server, and bash (or equivalent is your SHELL).
    * You have a standard .bashrc 

## Setup:
    * install wpgitupdater and other tools in $HOME/bin directory and add that to your PATH
    * install git 
    * copy the contents of this project's SHELL/bin into $HOME
    * create a symlink in $HOME pointing to the directory on your host where your WordPress instances are installed.
    * create a symlink with a short memorable name for each WP instance (I use Art,Bot,ELA,MKB,DTDev)
    * for each WP instance create a shell script called go<instance>  (eg. goMKB) using goMKB as a model
    * 

## SSH key setup
    * GitHub requires that each repository have a unique ssh key 
    * Create a new ssh key and store the private and public keys in your ~/.ssh directory (eg id_cw_mkb_github,id_cw_mkb_github.pub)
    * Register your public key in the GitHub Settings of your repository, then choose 'Deploy keys' in sidebar. 
    
## Selecting a specific WP instance in bash
    * Once logged into the machine and in $HOME directory...
    * Run the shell commands to setup for a specific instance (eg.  $ . ./goMKB) 
    * That should show you which goXXX script you are running, then the directory pathname of the instance.
    * It also should query and display the PID for the ssh agent, then add the approprate ssh certificate.  
    * Finally it will setup variables db, un, and MYSQL_PWD with the database name, the username, and password.
    * You will end up with your current directory being the public_html directory of your GH instance.
    * If you have not already create them, create three directories named .data, .pages, and .posts 

## On a regular basis, you can check if any files have been added or changed in your instance:
    * Once logged into the machine and in $HOME directory...
    * Run the shell commands to setup for a specific instance (eg.  $ . ./goMKB) 
    * You should now be in the public_html directory 