# Introduction
- For this project, you have to clone their Git repository on **their station**.
## Auxialiary Info
- encryption key: **passWORD123**
- root password: **born2beROOT**
- user (password): **isojo-go** (**born2beROOT**)

# Mandatory Part
## Check Delivered work
[ ] Ensure that the "signature.txt" file is present at the root of the cloned repository.
[ ] Check that the signature contained in "signature.txt" is identical to that of the ".vdi" file of the virtual machine to be evaluated.
- As a precaution, you can **duplicate** the initial virtual machine in order to keep a copy.
- Then, start the virtual machine to be evaluated.

## Project overview
- During the defense, a script must display information allevery 10 minutes. Its operation will be checked in detail later.
- The student being evaluated should explain to you simply:
  [] How a virtual machine works.
  [] Their choice of operating system.
  [] The basic differences between CentOS and Debian.
  [] The purpose of virtual machines.
  [] The difference between aptitude and apt, and what APPArmor is.

## Simple setup
[] A password (encryption key) will be requested before attempting to connect to this machine.
[] Ensure that the machine does not have a graphical environment at launch.
[] Login with a user. This user must not be root.
[] Check that the UFW service is started with the help of the evaluator.
[] Check that the SSH service is started with the help of the evaluator.
[] Check that the chosen operating system is Debian or CentOS with the help of the evaluator.

## User
[] Check that the user has been added and that it belongs to the "sudo" and "user42" groups.
[] Create a new user & assign it a password of your choice, respecting the subject rules.
[] Check the locations of the password rules.
[] Create a group named "evaluating".
[] Add the new user to the "evaluating" group.
[] Ask the student being evaluated to explain the advantages of this password policy, as well as the advantages and disadvantages of its implementation.
[] Check that the hostname of the machine is correctly formatted as follows: login42 (login of the student being evaluated).
[] Modify this hostname by replacing the login with yours, then restart the machine.
[] Compare partitions for the virtual machine. Note: if thestudent evaluated makes the bonuses, it will be necessary to refer to the bonus example.
[] Ask for explanation of how LVM works and what it is all about.

## SUDO
[] Check that the "sudo" program is properly installed on the virtual machine.
[] The student being evaluated should now show assigning your new user to the "sudo" group.
[] Ask for explanation on the value and operation of sudo using examples of their choice.
[] Show the implementation of the rules imposed by the subject.
[] Verify that the "/var/log/sudo/" folder exists and has at least one file. 
Check the contents of the files in this folder, You should see a history of the commands used with sudo.
Finally, try to run a command via sudo. See if the file (s) in the "/var/log/sudo/" folder
have been updated.
If something does not work as expected or is not clearly explained, the evaluation stops here.
UFW
Remember: Whenever you need help checking something, the student being evaluated
should be able to help you.

- Check that the "UFW" program is properly installed on the virtual machine.
- Check that it is working properly.
- The student being evaluated should explain to you basically what UFW is and the
value of using it.
- List the active rules in UFW. A rule must exist for port 4242.
- Add a new rule to open port 8080. Check that this one has been added by listing the active rules.
- Finally, delete this new rule with the help of the student being evaluated.
If something does not work as expected or is not clearly explained, the evaluation stops here.
SSH
Remember: Whenever you need help checking something, the student being evaluated
should be able to help you.

- Check that the SSH service is properly installed on the virtual machine.
- Check that it is working properly.
- The student being evaluated must be able to explain to you basically what SSH is and
the value of using it.
- Verify that the SSH service only uses port 4242.
- The student being evaluated should help you use SSH in order to log in with the newly created user.
To do this, you can use a key or a simple password. It will depend on the student being evaluated.
Of course, you have to make sure that you cannot use SSH with the "root" user as stated in the subject.
If something does not work as expected or is not clearly explained, the evaluation stops here.
Script monitoring
Remember: Whenever you need help checking something, the student being evaluated
should be able to help you.

The student being evaluated should explain to you simply:
- How their script works by showing you the code.
- What "cron" is.
- How the student being evaluated set up their script so that it runs every 10 minutes
from when the server starts.
Once the correct functioning of the script has been verified, the student being evaluated
should ensure that this script runs every minute. You can run whatever you want
to make sure the script runs with dynamic values correctly. Finally, the student being evaluated
should make the script stop running when the server has started up, but without
modifying the script itself. To check this point, you will have to restart
the server one last time. At startup, it will be necessary to check that the script
still exists in the same place, that its rights have remained unchanged, and that it
has not been modified.
If something does not work as expected or is not clearly explained, the evaluation stops here.
Bonus
Evaluate the bonus part if, and only if, the mandatory part has been entirely and perfectly done, and the error management handles unexpected or bad usage. In case all the mandatory points were not passed during the defense, bonus points must be totally ignored.

Bonus
Check, with the help of the subject and the student being evaluated, the bonus
points authorized for this project:
- Setting up partitions is worth 2 points.
- Setting up WordPress, only with the services required by the subject,
is worth 2 points.
- The free choice service is worth 1 point.
Verify and test the proper functioning and implementation of each extra
service.
For the free choice service, the student being evaluated has to give you a
simple explanation about how it works and why they think it is useful.
Please note that NGINX and Apache2 are prohibited.
