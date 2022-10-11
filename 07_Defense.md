# Introduction
- For this project, you have to clone their Git repository on **their station**.
## Auxialiary Info
- encryption key: **passWORD123**
- root password: **born2beROOT**
- user (password): **isojo-go** (**born2beROOT**)

# Mandatory Part
## Check Delivered work
- [x] Ensure that the "signature.txt" file is present at the root of the cloned repository.
- [x] Check that the signature contained in "signature.txt" is identical to that of the ".vdi" file of the virtual machine to be evaluated.

- As a precaution, you can **duplicate** the initial virtual machine in order to keep a copy.
- Then, start the virtual machine to be evaluated.

## Project overview
During the defense, a script must display information allevery 10 minutes. Its operation will be checked in detail later.
The student being evaluated should explain to you simply:
- [x] How a virtual machine works.
- [x] Their choice of operating system.
- [x] The basic differences between CentOS and Debian.
- [x] The purpose of virtual machines.
- [x] The difference between aptitude and apt, and what APPArmor is.

## Simple setup
- [x] A password (encryption key) will be requested before attempting to connect to this machine.
- [x] Ensure that the machine does not have a graphical environment at launch.
- [x] Login with a user. This user must not be root.
- [x] Check that the UFW service is started with the help of the evaluator.
- [x] Check that the SSH service is started with the help of the evaluator.
- [x] Check that the chosen operating system is Debian or CentOS with the help of the evaluator.

## User
- [x] Check that the user has been added and that it belongs to the "sudo" and "user42" groups.
- [x] Create a new user & assign it a password of your choice, respecting the subject rules.
- [x] Check the locations of the password rules.
- [x] Create a group named "evaluating".
- [x] Add the new user to the "evaluating" group.
- [x] Ask the student being evaluated to explain the advantages of this password policy, as well as the advantages and disadvantages of its implementation.
- [x] Check that the hostname of the machine is correctly formatted as follows: login42 (login of the student being evaluated).
- [x] Modify this hostname by replacing the login with yours, then restart the machine.
- [x] Compare partitions for the virtual machine. Note: if thestudent evaluated makes the bonuses, it will be necessary to refer to the bonus example.
- [x] Ask for explanation of how LVM works and what it is all about.

## SUDO
- [x] Check that the "sudo" program is properly installed on the virtual machine.
- [x] The student being evaluated should now show assigning your new user to the "sudo" group.
- [x] Ask for explanation on the value and operation of sudo using examples of their choice.
- [x] Show the implementation of the rules imposed by the subject.
- [x] Verify that the "/var/log/sudo/" folder exists and has at least one file. 
- [x] Check the contents of the files in this folder, You should see a history of the commands used with sudo.

## UFW
- [x] Check that the "UFW" program is properly installed on the virtual machine.
- [x] Check that it is working properly.
- [x] Ask what UFW is and the value of using it.
- [x] List the active rules in UFW. A rule must exist for port 4242.
- [x] Add a new rule to open port 8080. Check that this one has been added by listing the active rules.
- [x] Delete this new rule with the help of the student being evaluated.

## SSH
- [x] Check that the SSH service is properly installed on the virtual machine.
- [x] Check that it is working properly.
- [x] Ask what SSH is and the value of using it.
- [x] Ask what Verify that the SSH service only uses port 4242.
- [x] Use SSH in order to log in with the newly created user.
- [x] Make sure that you cannot use SSH with the "root" user as stated in the subject.

## Script monitoring
Ask the user:
- [x] How their script works by showing you the code.
- [x] What "cron" is ans how set up the script so that it runs every 10 minutes.
- [x] Once the correct functioning of the script has been verified, the student being evaluated should ensure that this script runs **every minute**.
- [x] Stop running the script without modifying it, restart, check that the script, still exists in the same place, that its rights have remained unchanged, and that it has not been modified.


# Bonus
- [x] Setting up partitions is worth 2 points.
- [x] Setting up WordPress, only with the services required by the subject, is worth 2 points.
- [x] The free choice service is worth 1 point.
