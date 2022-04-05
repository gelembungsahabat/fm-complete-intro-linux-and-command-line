# Subcommands
Sometimes you need to invoke a command within a command. Luckily bash has you covered here with the ability to run subcommands.

`echo I think $(whoami) is a very cool user # I think ubuntu is very cool`
The `$()` allows you to put bash commands inside of it that then you can use that output as part of an input to another command. In this case, we're using `whoami` to get your username to echo that affirming message out. Let's a more practical one. Let's say you wanted to make a job that you could run every day to output what your current uptime was. You could run this command

`echo $(date +%x) – $(uptime) >> log.txt`
The `+%x` part is just saying what date of format you want, and I got that from reading `date --help`. So end printing something like

`06/17/20 – 21:38:34 up 8:51, 1 user, load average: 0.00, 0.00, 0.00`
There are far more useful logs to write but you can see here the power of subcommands. Note you can also use backticks like ` instead of $() but it's preferred to use the $() notation. Notably, you nest infinitely with $(). For more reasons, read here.