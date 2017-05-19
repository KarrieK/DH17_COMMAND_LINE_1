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

OS X - If you're running OS X then you need to install iterm from the app store
Linux - No need to do anything, terminals are built into the operating system.
Windows - has a built-in shell, called Command Prompt, which emulates their older operating system, DOS. You can use Cgywin in Windows to emulate a bash environment

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

## Moving forward  ##

We are in our new directory so what now?

Hopefully you grabbed the two files in the repo and they are downloaded onto your machines. Well I think we should take both those files and move them into the our new directory.

```$ cd ../..
$ pwd
$ cd Downloads
$ ls
```

See your files? Oh good now let's move them using the mv or move command.

`$ mv (FOLDER NAME) ~/Desktop/command_line`

Now take a look, did it work?

Let's read in those files into the terminal to see what's in them. To do that we're going to use cat.

So let's try `cat HonoursLists2015_2016.csv`

What have we got?

## Other unix commands  ##

touch - creates a new text files
nano - allows you to edit a text file
cp - copies a file or directory
rm - removes a file or directory
man - gives you the manual for a command
rmdir - removes an empty directory
grep - general regular expression (like in R)

## Matching csvs  ##

Comparing csvs and searching for matches is really powerful and can lead to some great leads to follow. However be extremely careful false positives are very real and are a recipe for libel if results are not thoroughly check and validated.

We are going to use the python library csvmatch to hunt for results. But we need to install pip a package manager and then the library csvmatch.

Let's grab pip $ sudo easy_install pip

To install type pip install csvmatch and wait.

Let's grab our two files HonoursLists2015_2016.csv and Political_Donations_2014_2016.csv and see if there are any exact matches in there:

$ csvmatch HonoursLists2015_2016.csv Political_Donations_2014_2016.csv

So there is too much data there for the terminal to handle so we need to specify which columns.

$ csvmatch Political_Donations_2014_2016.csv HonoursLists2015_2016.csv --fields1 DonorName --fields2 Name

Hmm let's try to fuzzy match that and output the results to csv

$ csvmatch Political_Donations_2014_2016.csv HonoursLists2015_2016.csv --fields1 DonorName --fields2 Name --fuzzy > results1.csv

## Resources ##

If you want to dig deeper and explore the awesome world of command line tools then here are a couple of links to get you started.

csvmatch docs - https://github.com/maxharlow/csvmatch
More unix commands - https://www.techonthenet.com/unix/basic/
Data tools - https://github.com/clarkgrubb/data-tools
##Contact me

Email: karrie.anne.kehoe@gmail.com Twitter: @karriekehoe

