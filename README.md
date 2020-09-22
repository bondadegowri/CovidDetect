# CovidDetect

INSTALLING PYTHON


Version: 1.1.0
Date: 2020-09-20
Author: Gowri Bondade

Tarun raj


Installing Python On Windows
The preliminary step consists in installing the Python interpreter (i.e., the "master program") on your computer.

Installing Python is a one-time operation. If you already installed Python in the past (for example, to run a different program), you do not need to install it again, and you can skip to the next section.

Let's assume we need to install Python 3.

Step 1: Download The latest version of Installer from https://python.org/:

Click on the Download > Latest Python 3.6.0

You will get a page listing all the new features of Python 3.6.0 (64 or 32 bit based on PC).

Step 2: Install Python
Double-click on the file you just downloaded to start the installation wizard:

Python 3.6.0 installer

By default, the Add Python 3.6 to PATH option is disabled, please should select it, it makes running Python programs easier.

Most users should click the Install Now button, which installs Python with the default settings.

Step 3: 
Now open the Command Prompt, locate the Command Prompt icon in your Start menu (or use the search bar):

The prompt line always starts with the location of the working directory, it is the folder where the command prompt is currently acting upon.

>>> python test.py

You should not type the $ character, it is just a placeholder for your actual prompt. For any practical purpose, you can mentally replace the $ with your actual prompt, like C:\Users\IEUser> in the example above, as if the documentation was as follows:

C:\Users\IEUser> python my_awesome_program.py
(You will actually type only python my_awesome_program.py and hit the Enter/Return key.)

The Three Safety Rules
By issuing commands on the Command Prompt, you can accidentally delete your own files or damage Windows, so you must be careful.

Do not be afraid or discouraged: you do not stop using knives just because you can cut your fingers with them!

By following Three Safety Rules, you can operate the prompt safely:

Never issue a command without understanding what it does, and only run programs obtained from developers that you trust.
If anything happens in the prompt that you do not understand, you can simply click on the "X" on the right top corner to close the Command Prompt window (and hopefully nothing bad will happen to your files).
Always copy your Python program in a separate folder, and always make copies of your input files in it, so that you can just throw away the Python program folder if something goes wrong, and start over.
Changing The Working Directory (cd)
As said above, the command prompt normally opens in the home directory of your user:

Command Prompt window

If you want to change the current working directory, you can use the cd command. For example, to move to the C:\ directory (the root directory of your C: drive), you type cd C:\ and press the Enter/Return key:

Command Prompt window

Notice that the prompt changed to C:\>.

Listing The Contents Of The Working Directory (dir)
If you want a list of the files or subdirectories contained in the current working directory, issue the dir command, without arguments:

Command Prompt window

The prompt shows a list of directories and files that are contained in the C: drive: in the above screenshot they are BGinfo, PerfLogs, ..., Windows.

At this point, if you want to enter the Users directory, you can simply type cd Users, and so on.

If you want to go up one level, type cd .. (two full stop character). For example, if you are in C:\Users\ and give a cd .., you will end up in C:\.

If you want to clear the prompt window, use the cls command.

Checking That Python Is Installed Correctly
If you selected the Add Python to PATH option, you can run the Python interpreter (and any Python program) from any current working directory.

To check this, give the python --version command:

Python non-interactive execution

The Python version will be printed (e.g., Python 3.6.0) and you will get back to the Windows prompt. You just ran Python in non-interactive mode, meaning that you provided a precise command ("Python, print the version number you are"), the Python interpreter performed what you asked for, and then it returned control to the Command Prompt of Windows.

The non-interactive mode is how most Python programs work.

If you forget to add the --version parameter after the python command, you will enter the interactive Python shell instead:

Entering Python interactive shell

Notice how the prompt changed to >>>.

To exit the Python shell, and return to the Command Prompt, just type quit() and hit the Enter/Return key:

Leaving Python interactive shell

Discussing the interactive shell is beyond the scope of this guide, since most programs you are interested in are non-interactive.

Running A Python Program
Excellent, now you have all the tools required to run a Python program on the command line.

As an illustration, I will use my simple Python script export-kobo, which reads annotations and highlights from the database file of a Kobo eReader device (KoboReader.sqlite), and prints them on the prompt or exports them to an output file.

Step 1: Download The Source Code
First, download the source code of the Python program you want to run.

This usually implies downloading either a single Python source code file (with extension .py), or a ZIP file containing several Python source code files and other resource files that you need to uncompress somewhere on your disk.

The exact details depend on your Python program, hence be sure to carefully read its install documentation. You can download the prescribed files with your browser, and then copy/uncompress them using the Windows graphical file manager.

In our example, we download the raw file export-kobo.py from the GitHub repository.

Remember Safety Rule 3 ("copy your Python files into a separate folder")?

We put the downloaded export-kobo.py file in a new folder C:\export-kobo:

Running a Python program

Note that we also copied the KoboReader.sqlite file (the input of our Python program) from our Kobo eReader to the same folder.

Step 2: Open A Command Prompt And cd There
Then, open a Command Prompt as explained above, and change the current working directory to the folder where you put your Python program source files.

In our example, cd C:\export-kobo:

Running a Python program

A simpler alternative to using the cd command takes advantages of the Windows file explorer. Just navigate the file explorer to the folder where your Python code is:

Opening a prompt from file explorer

and select the File > Open command prompt > Open command prompt menu:

Opening a prompt from file explorer

you will get a new Command Prompt window, already located at the correct directory:

Opening a prompt from file explorer

Step 3: Run The Python Program
At this point, we are ready to run our program.

Type python export-kobo.py KoboReader.sqlite --list and hit Enter/Return:

Running a Python program

The Python interpreter will load our export-kobo.py program, and run it with arguments KoboReader.sqlite and --list.

Clearly, the semantics of the arguments vary from program to program, depending on what each program is supposed to do.

In our case, export-kobo.py will read the file whose name is passed as the first parameter (KoboReader.sqlite) and it will list (--list option) the titles of all the eBooks with annotations or highlights in the database.

If we specify different command arguments, for example python export-kobo.py KoboReader.sqlite --csv --output exported.csv, we will get a different behavior:

Running a Python program

In particular, this second command exported all the information contained in the KoboReader.sqlite file into the newly created file named exported.csv in CSV format:

Running a Python program

You must check the documentation of your Python program to know the semantics of its arguments.

Usually, if you run a Python program without arguments you will get a synopsis of the accepted arguments:

Running without arguments shows the synopsis

If a -h or --help argument is given, then a more verbose help message will be printed:

Running with -h shows an help message

Congratulations, now you should be able to download and run a Python program on your own!
