## Groups
Just like we can add and subtract permissions from a user in Linux, we can actually do it for whole cohorts of users using groups. This is useful for many reasons. Let's say you have a server that everyone connects to get documents. You could have one cohort of users that just needs to read / download the documents. In this case, we could make a readers group and give them read-only permission to all files. They'll never need to (or be able to) create new files. Now if a hacker gets ahold of their credentials, they can only read files and not wreck your server. And when we add a new user, we just add them to the readers group and that's it! If we need to later modify it that readers can add files to just one directory, we can easily make that happen by adding write permissions to one directory for the readers. See how this can streamline things?

Some groups has special privileges, like the `sudo` group. These users can now `sudo` whenenver they need to. Let's add our user brian to the sudo group. Run `sudo usermod -aG sudo brian` (or `sudo usermod --append --groups sudo brian` if you want the long form) from the ubuntu account. usermod allows you to modify user accounts and `-aG` allows you to append new groups to the user. In this case, we made it so brian is now a sudoer. Try this now.

```su brian
sudo whoami```

And now you can see it respond root, which means you've successfully … sudone?