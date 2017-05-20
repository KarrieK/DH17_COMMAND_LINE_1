# Introduction to the Command Line #

Add to your data tool box by harnessing the mighty power of the command line, the little black box full of potential. We'll teach you how to navigate your operating system, mouse free, manage files and folders, sanity check your data and manipulate csvs. The possibilities are endless the future is bright!

## Why the command line? ##

* manage files and folders
* sanity check your data
* fast and powerful
* automate tasks
* version control - push scripts to your github
* changes the way you think about computing

## What is the command line? ##

The command line is an interface to the computer which allows us to instruct the computer by typing commands directly to an interpreter. It allows us to navigate around in the filesystem and perform tasks without using the mouse.

If you run OS X or a Linux operating system then you are in luck, the unix command line is going to be your best friend. The bad news is that if you run Microsoft Windows your life is going to be a lot tougher, as the DOS command line is not as helpful or powerful (my opinion).

## What do you need? ##

* OS X - If you're running OS X then you need a working bash shell. iTerm is a great terminal - you can grab it here https://www.iterm2.com/downloads.html
* Linux - No need to do anything, terminals are built into the operating system.
* Windows - has a built-in shell, called Command Prompt, which emulates their older operating system, DOS. You can use Cgywin in Windows to emulate a bash environment

## Commands we're going to cover ##

* pwd - print working directory
* ls - list
* cd - change directory
* mkdir - make directory
* mv - move
* cat - outputs the file to the terminal
* head - outputs the first ten lines to the terminal
* touch - creates a new text file
* nano - writes to text file


## Getting started ##

Ok first thing's first. Open up your terminal and take a look. There should be some text at the top of the terminal saying something like this:

```Last login: Fri May 18 13:32:59 on ttys005 Karries-MacBook:~ karrie$```

The dollar sign $ is called a shell prompt, it's where we're going to input commands.

Well we are now speaking to the operating system but we need to know where we are on that system.

To do that we are going to use the following command:

pwd - stands for print working directory. This will tell us where we are within the file system
The terminal tells me i'm at /Users/karrie - this is the home directory. Contained within this directory are deeper directories like Desktop, Downloads etc...

So we know where we are at but what is in our home directory?

ls - is short for list. We are now asking the machine to list all the contents of that directory
Our terminal lists lots of files and directories but how do we know which is which? The simple answer is to look for a file extension. If the name has an extension at all like .py, .R or .csv.

ls -a - reveals hidden files so you see the full contents of your directory
ls -t - sorts files in order of newest first
So I now I know what's in my home directory but I want to move into my desktop so I can see what's in there - to do that I have to navigate into that directory.

cd - change directory. This command allows us to move into a chosen directory so our command should look like this:
`$ cd Desktop`

Now we are in Desktop and want to look at the work we did today in class. We need to move into the correct folder containing our coursework.

But are we in the correct place? Check with the pwd command

pwd - stands for print working directory
If we want to move back one directory we can do so easily using cd .. or two directories cd ../.. or Or cd ~ to return to the home directory

Ok so maybe we want to move some of our files into a new directory. Let's make that new directory first

mkdir - make directory. This command makes a new directory in the filesystem at the location you have navigated to
Let's create a new directory and call it 'EIJC_Data':

`$ mkdir EIJC_Data`

What command will tell us if that worked?

Let's move into that directory.

## Data Time  ##

Now we know the basics, let's grab some data and read it into our terminal. 

Download the asylum data in the folder

```$ cd ../..
$ pwd
$ cd Downloads
$ ls
```

See your file? Let's move it into the right folder using mv

`$ mv Asylum_Data.csv ~/Desktop/EIJC_Data`

Now take a look, did it work?

Let's read in those files into the terminal to see what's in them. To do that we're going to use cat.

So let's try `cat Asylum_Data.csv`

What have we got?

You can use CTRL+Z to kill the cat command at any point - way too much information to make any real sesne of it. 

So let's use head to look at the first ten lines

## Documentation ##

Let's create a text file and remind ourselves where our data came from and when we grabbed it in case we need to know later. 

To do that we're going to use touch

`$ touch doc.txt `

Now we have created an empty text file - time to write something in it. 

To edit a text file we use nano

`nano doc.txt`

Add the link we downloaded the data from and the date we downloaded it from

To exit ctrl-x

Save and close

## Other unix commands  ##

* cp - copies a file or directory
* rm - removes a file or directory
* man - gives you the manual for a command
* rmdir - removes an empty directory
* grep - general regular expression (like in R)

## Next class  ##

In the next class we're going to use the python library csvkit to take a closer look at our data

## Resources ##

If you want to dig deeper and explore the awesome world of command line tools then here are a couple of links to get you started.

* Cheat sheet - https://learncodethehardway.org/unix/bash_cheat_sheet.pdf
* More unix commands - https://www.techonthenet.com/unix/basic/
* Data tools - https://github.com/clarkgrubb/data-tools

## Contact me ##

Email: karrie.anne.kehoe@gmail.com Twitter: @karriekehoe

