# PATH
Okay, so right now you have to give a path to be able to run gen_files.sh. What if we want to be able to run gen_files from anywhere on our computer? We can do that!

Your user a variable set called PATH. Your PATH is a series of locations of where programs live. If I say python3, it goes through each of those locations and checks for anything called python3. If there are two, it uses the first one it finds (the path furthest left in the path.)

You can see your PATH if you run `echo $PATH`. You should see something like `/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin```` (it may not be exactly this.)

In general I don't mess any of those directories. All of those are system wide bin directories (if you had more than one user they'd share them.) So a good idea is to have your own ~/bin directory. So let's do that.

```cd ~
mkdir bin
mv gen_files.sh bin/gen_files
PATH=~/bin:$PATH
echo $PATH
gen_files
```
Hooray! Now it works! We added ~/bin to our path so now bash will try to execute anything we put in there. We added ~/bin to the front of our path and that's a good idea. If, for example, wanted a different rm program than the default one, we don't want to mess with the system one, just ours. We would want ours to "shadow" the system one and to not mess with everyone else's rm.

When we set the PATH, we used PATH to define itself. Keep in mind that bash will replace that $PATH before it runs our command so by the time we try to set the variable it's just a string. That's why that works.

Lastly, we only set the PATH for just this session. Once we close our terminal, it'll go away. However we can add this line to our .bashrc and it'll always get set! Run `vi ~/.bashrc` (or nano) and add this line somewhere:

`PATH=~/bin:$PATH`
Multipass already had a lot of stuff in there for me so don't get overwhelmed. You can put that line just about anywhere. Whenever you make a change to .bashrc you have to rerun it or it won't take effect on your current session. Run `. ~/.bashrc` and you'll be set.

## Comments
If you want to add comments, you just add # and then from there you can put anything after it. You've probably notice me doing it before this.