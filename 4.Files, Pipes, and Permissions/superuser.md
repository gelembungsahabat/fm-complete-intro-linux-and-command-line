## Superuser
ubuntu is a user and can only do things that a normal user can do. For example, a user cannot create a new user. Try `useradd brian` (or change brian for whatever you want the name of the new user to be.) You 'll see something saying "Permission denied". This is because only the superuser can add new users. So let's try that. Run `sudo su`. We'll talk about sudo in a sec but `su` is switch user. Now try running `whoami` again. It should say "root". The root user is the superuser. Now we have ultimate power: the superuser has no restrictions on what it can do. Try running `useradd brian` and you'll see you run it with no problem.

What we did, sudo su is usually not what you want to do. When you do things as root, it means usually that only root in the future will be able to modify and delete files it makes. It also means that if you fat finger a command and accidentally type something wrong, you really can burn down the house. It's like using a flamethrower to start a grill: you can do it but there's a good shot you're taking the house down with you.

To get out of being root, just hit CTRL+D or run `exit`. You should be back to being ubuntu.

