## Shell Scripting Basics
### Task 1: First Script
#### What happens if you remove the shebang line?
the script may still work in many shells because your current shell tries to execute it, but behavior can become inconsistent, and some systems may show errors if the shell cannot determine the interpreter.
### Task 2: Variables
#### Try using single quotes vs double quotes — what's the difference?

ubuntu@DESKTOP-7CJ1O5G:~$ ./greet.sh

Hello, I am Arya Parab, working in DevOps Engineer

Hello, I am $name, working in $role
