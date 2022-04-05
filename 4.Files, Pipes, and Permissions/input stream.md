## Input stream (stdin) 
Okay, so now we've talked exhaustively about the output streams, let's chat a minute about input streams.

stderr and stdout direct the text from a program to a file. With stdin, we can direct the contents of a file into a program via the stdin. Try this

cat < ls.txt
Now, again, not entirely useful, since cat ls.txt would have done the same thing. But let's say it's a very long file and we want to find one very specific line. We could do this:

grep "error-log.txt" < ls.txt
We'll talk about the ins and outs of grep in a later chapter but for now it's enough to know it lets you find things in a text stream. In this case, we took the contents of ls.txt and connected that stream to grep which grep then looked for a line that contained "error-log.txt" in it. So that's what < does, it take a file and puts that into stdin so a program can use it.

## Using stdin and stdout
What if we want to have both stdin and stdout and then throw away the errors?

grep "error-log.txt" < ls.txt 1> ls2.txt 2> /dev/null
Just like that! Order isn't important.