# Pipes
Okay so we've exhausted you can do with just files but what if we want to use the output of one program into another? Enter the pipe (sometimes called vertical bar,) |. This takes what one program outputs and puts it into the next one. This opens up a lot of possibilites. Let's redo that one we had above with grep using cat and |.

`cat ls.txt | grep "error-log.txt"`
cat will concatentate ls.txt to stdout and then | will take the output of that and run that as stdin to grep.

Let's try another using ps. We'll get to processes later but ps outputs all running processes. It's usually a very long list since Linux has a lot running all the time. Try running ps aux and see how long it is. It can be much longer too if you're running a server. Notice the last thing it outputs is the ps aux command itself that you used to find it. Let's use grep to find just that line and nothing else. Try this:

`ps aux | grep "ps aux"`
This should output two lines, the ps aux call and the grep we're running to find that ps aux. A little self referential but the point here is that we're able to find just what we need and leave the rest behind. And we're doing that with the power of pipes. ps aux find all processes and outputs that to stdout. We then take that stdout and run that as the stdin to grep. grep then finds just the lines it needs and outputs just those to its stdout. At this point we don't have anything else redirecting output streams so it gets output to the terminal window. We absolutely could redirect that out to a file using 1>.

Let's a bit trickier one. If you do rm -i *.txt, it'll try to remove all files with .txt extensions. It'll all confirm with you on each one to say either y for yes or n for no. Try it and say "n" and hit enter for each one. Notice afterwards you won't have deleted anything.

Lots of Linux programs function this way of answering y or n questions. Someone got sick of doing it and wrote a program to just answer y nonstop called yes. We looked at this before. But now let's yes it. Let's make it say n to all those questions.

`yes n | rm -i *.txt`
The first command, yes n outputs infinite ns to stdout. rm -i *.txt uses those from stdin to answer n to every question it asks. Pretty cool, right?

We'll use pipes a lot. By this we can use smaller commands like grep, cat, yes, and other to make higher level programs. We're using bash to program! Bash scripting.z