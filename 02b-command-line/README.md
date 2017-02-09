# Learn to Use the Command Line!
Part of becoming a developer means using to learn the tools that developers use. The first and potentially most important tool, is the command line.

## What is the Command Line?
The command line is a way of controlling a computer without a mouse or a GUI (Graphical User Interface). Before Apple Computers started building machines with icons and folders you could click on, the only way to interact with your computer was through the command line.

[BEFORE PICTURE] [AFTER PICTURE]

As developers, we use the command line because it's a lot faster and more powerful that the GUI. No more clicking around like a noob!

## What can I do?
What *can't* you do?!? The command line is incredible - pretty much any interaction you have with your computer, you can have in the command line. In this lesson we're going to learn the basic commands: creating files and directories, moving folders, changing directories, and listing the contents of a folder.

## Get Started
In Cloud9 (or the terminal), you'll see your command line at the bottom of the screen. Click on it and the cursor (where you type) will light up. Next to the cursor, you'll see your "prompt" - the prompt tells you "Hey, this is where you want to type." We can customize our prompt (more on this later) to make it show different pieces of information.

**Note:** "Directory" and "Folder" are the same thing.

### Trying some Commands
+ **`ls` - List:** Typing `ls` and then hitting enter will list all of the (visible) files and folders in a directory. To show hidden files, type `ls -a`.

![List Itemts](https://drive.google.com/open?id=0B0hFY6ZxooIjRlJSUVcxQlZoODA)
+ **`pwd` - Print Working Directory:** This will list the directory that you are currently "in". You know how when you are in the finder and you double click a folder, and then you are suddenly "in" the folder and can see it's contents? Same thing here. `pwd` will tell you what directory you are currently "in."
+ **`mkdir directory_name` - Make a Directory:** This command allows us to make a brand new directory, in your current location. Let's say you're in your "documents" directory, and type `mkdir photos`. This would create a photos directory *inside of the documents directory.*
+ **`cd directory_name` - Change Directory:** Following from the example above, if we want to move **in to** a directory, type `cd directory_name` where "directory_name" is the name of the folder that you're moving into. To move **out of** a directory (up one level), type `cd ..` the `..` means "one level up". To change back to your "home" directory, you can always type `cd ~`.
+ **`touch file_name` - Make a new File:** The `touch` command allows you to make a new *file*. For example, if we wanted to create a new index page for our website in HTML, we'd type `touch index.html` Make sure to give each new file an extension (like .rb, .js, .html, .css) depending on the type of the file.
+ **`mv file_or_folder_name destination` - Move:** If you want to move a file or folder, use the `mv` command followed by the name of the file you want to move and then the destination. Make sure the destination is a directory that is visible to you from your current working directory. **Warning:** If you move a file to a directory that does not exist or is incorrectly pathed, then the file itself will have its name changed to the destination's name.
+ **`rm -rf directory_name` - Remove a directory:** Use `rm -rf` and a directory's name to remove it and all of its contents. Careful with this one!
+ **`rm file_name` - Remove a file:** Use `rm` to remove a file. Note: Files that are removed cannot be brought back!
**You Do:** From your command line, navigate to your home directory (`cd ~`) and create a new development directory (`mkdir development`).

+ Tips, Tricks and Resources
Codeacademy
etc...
