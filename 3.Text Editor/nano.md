# nano
nano is an old open source text editor that itself was an evolution from a previous text editor called pico. Pico was the text editor of the command-line email client Pine that people grew to love so much that they used it for everything. Because Pine was licensed in such a way that Debian wouldn't include it with its distro, Chris Allegretta re-implemented under the name TIP (Tip Isn't Pico, computer scientists love recursive acronyms) it eventually was renamed to nano.

Due its tiny size, light weight, and permissive license, nano is included on just about every Linux/Unix-like OS and is frequently the default text editor, even on tiny little embedded devices where even vim is too much. As such, it's a good tool to have your tool belt if you need to do some light text editing.

So let's get a brief tour of what you can do in nano.

Make sure you're in your home directory. If not, type cd ~ to get there. Type nano textfile.txt. This will create a new file called textfile.txt in the directory in your folder. Type something in there. I put "Hi, this is Brian. You're in a text file." Once you've written what you want to, take a look at the bottom bar and you'll see a bunch of available actions.

<br>
![nano](https://btholt.github.io/complete-intro-to-linux-and-the-cli/static/7c2c5569f855f6137bba414f9577cd48/afa26/nano.png)

<br>
The ^ represents CTRL. So if you want to "get help", you'll hit CTRL + G. The M- character represents the Meta key which keyboards don't have anymore. Given that, terminals have had to work around that. If you're on Windows, that key will be the Alt key. If you're on macOS, unfortunately the Option key has other uses already (making alternative characters like ¢∞§ etc) so you have to use Esc (weird, I know.) As a macOS user, I just deal with this because it's really only nano where it's awkward. There is a way to make your terminal use Option if you feel strongly about it but I don't. I really only use nano when I have to.

Okay so here we are. We want to save our file. If you see at the bottom ^O is "Write Out" which in reality just means save. You'll find in these older editors they use the term buffer liberally. What a buffer is that what you've written to that file before you save isn't actually saved in the file which means it's being held somewhere else. That "somewhere else" is the buffer which is just space in memory.

So hit CTRL + O. It'll make sure you don't want to save it somewhere else and a few other options. We should be good with it so just hit enter. Now that we've completed what we wanted to do, hit CTRL + X to exit nano entirely. If you wanted to open the file again, you'd hit nano textfile.txt.

nano can obviously do significantly more than what I've shown you but any time I want to do "significantly more" I'll figure out how to use VSCode instead so I don't invest any more into nano or vim than that.