# Command Line Interface

Following are the basic commands that you should be familiar with to smoothly work on a remote system:

## Manuals

Most of the following commands have a man page. So if you want to quickly find the flags or how to run the command just run `man <command>` or, you know, google it.

## File Handling
`vim` - A cli text editor. Handy to quickly go through and edit files on a remote system.

`emacs` - vim's arch enemy. Serves the same functionality. There is a rivalry between the users of these two. Choose your side wisely.

`git` - This is a must learn tool for any self-respecting students who deals with code and hates files with name such as assignment_final_final_v4[3].py

<img src="../fire.png" data-canonical-src="https://www.instagram.com/p/8N8J8wRgPq/?utm_source=ig_web_copy_link" width="200" height="200" />

[Image Source](https://www.instagram.com/p/8N8J8wRgPq/?utm_source=ig_web_copy_link)

`grep` - Helps you quickly search, well, any text.

My go-to: `grep -inr <keyword> <file_path>`

`find` - Helps you quickly find a file using regex.

My go-to: `find <path> -iname <regex>`

`cat` - show the contents of a file on the terminal. Useful for a quick look without opening the file. Also useful if you want to seach for something in a file. Cascading with `grep` gets it done. Cascading is done using a pipe (`|`, the key above enter).

`touch` - Create an empty file.

## Process
`htop` - Very useful utility to monitor the resource usage. Also helps you see all the processes running.

`kill` - If you want to terminate a process just `kill -9 <pid>`. How do you get the pid? Use `htop/netcat` etc.

## Remote
`ssh` - You'll in your senior year. I shouldn't have to explain this!

`scp` - It's bascially `ssh+cp`. Let's you move files from remote <==> local.

`wget` - Download a page. See the help page. Interesting stuff.

## Utility

`history` - Don't remember the ip or a command. This command let's you see all your past sins.

`screen` - Let's you run programs in the background. I will repeat. Let's you run the programs in the background.

`tmux` - Similar to screen. Has a lot more useful features. I don't like it much :P

`ctrl` + `r` - Let's you search the history. So you don't have to open the file again and again to find the command that you always forget.

`ctrl` + `l` - Clears the screen.

