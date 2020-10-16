---
layout: page
title: CLI Tutorial
doodle: /doodle.png
---

## Logging in
Run `ssh <USERNAME>@dsmlp-login.ucsd.edu`. Please, please read the next sentence. Replace `<USERNAME>` with your username.

## Current directory
Now you have logged in. How do you know where you are?
Run `$pwd`
This tells you your `p`resent `w`orking `d`irectory. 

## Listing all the files and directories
Run `ls` to list all the files in the current directory.

## Creating a directory
Now in this directory, you want to create another one with the name `MY_COOL_DIRECTORY`.
Run `mkdir MY_COOL_DIR`. `mkdir` stands for `m`a`k`e `dir`ectory. Now, run `ls` and make sure that the directory you created is indeed there.

## Moving around
You want to go into the directory you just created.
Run `cd MY_COOL_DIR`. cd stands for `c`hange `d`irectory.
What happens if you run jus `cd`? Do it! It takes you to your `home` directory. 

So, if you are ever lost. If you ever feel like you are in a sketchy neighbourhood with unfamiliar files with weird extensions, don't worry, just `cd` and you will be `home`.

## Creating file
Next, we want to create a file named `my_super_cool_file.txt`. There are a couple of ways of doing this. If you just want to create an empty file, you can simply `touch my_super_cool_file.txt`.
If you want to write something in the file, you can open it in a cli editor such as `vim` or `emacs`.

## Downloading a file
You found [this](https://github.com/ericmichael/cooltxt/blob/master/cool.txt) file on the internet and you absolutely cannot not have it.
Run `wget https://github.com/ericmichael/cooltxt/blob/master/cool.txt` to get the file.

## Moving a file
You meant to download the file in parent directory.
Run `mv cool.txt ..`. In linux, `.` represents the current directory, `..` represents the parent directory.

## Copying files/directories to/from server
Open another terminal on your laptop and go to downloads directory. If you are on windows google how to change the directory. Now we will copy a file from your downloads directory from your local machine to the server.
Run: `scp <file> <USERNAME>@dsmlp-login.ucsd.edu:MY_COOL_DIR/`