# Hashbang
Notice we didn't have to make gen_files.sh an executable file. That's because we're not actually executing it directly: we're executing bash or source (source and . are the same thing) and those are executing our program. But what if wanted to actually make it a new command that we didn't have to feed into source or bash? What if we could basically make it indistiguishable from a normal command like cp or curl? You can! Let's see how.

Open `gen_files.sh` and put this as the very first line. I bold that because it must be the first line.

`#! /bin/bash`
This line (called a shebang, hashbang, or many other things; often ! is called a bang in computing) lets bash know how to execute this file. It must be on the first line and it must start with `#!`. It's then always followed by the absolute path (meaning it starts with `/` and gives you the full path; you cannot give it a relative e.g. `./bash`). This works with Python, for example. If you want a script to executed by python3, you can find the path of any program by saying `which <command>`. So if we want to know where python3 is, we can say `which python3` and get the path from that.

Okay, so now we have a hashbang in place. However the file now needs the executable permission. Let's do that. Run `chmod 700 gen_files.sh`. Now you can run `./gen_files.sh` without anything running as the executable. We need the `./` because `gen_files.sh` isn't on our PATH yet (I'll explain that very shortly.)