## Installing VSCode

To install VSCode, first go to https://code.visualstudio.com/download. Select Windows/Mac based on what your computer is running on. Afterwards, follow the installer's directions, and wait a few minutes for VSCode to download. Double-click the VSCode icon to open it after it has finished installing on your machine. You will be prompted with a choice to either make a new project or open an existing folder. After opening a project on VSCode (I opened the starter code for CSE 12's first PA), your screen should look like this:
<img width="1127" alt="Screen Shot 2023-01-12 at 2 31 05 PM" src="https://user-images.githubusercontent.com/69327109/212196294-8c494886-eb7f-42ff-9aad-a8e8edf5a2aa.png">

## Remotely Connecting

To remotely connect to the CSE15L, enter the command *ssh cs15lwi23auw@ieng6.ucsd.edu* into your terminal, where cs15lwi23auw is replaced by your own username (in my case, cs15lwi23auw is my username). You will be prompted to enter your password, which you should have set beforehand (if you need to reset the password, visit https://sdacs.ucsd.edu/cgi-bin/gpquery. Afterwards, you should see the below message show on your terminal, which confirms that you've connected to the remote server.
<img width="681" alt="Screen Shot 2023-01-12 at 2 47 09 PM" src="https://user-images.githubusercontent.com/69327109/212197592-37d1ee54-4643-4b49-9d06-52eb071f260d.png">

## Trying out some commands

Once you are connected to the remote computer, you can execute commands on them and access their files. I tried general commands such as:
- *cd* to change directory
- *pwd* to see my current directory
- *ls* to list all files and folders in the current directory

As well as more specific ones such as:
- *cat /home/linux/ieng6/cs15lwi23/public/hello.txt* to print the contents of a file named **hello.txt**
- *cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/* to copy that same file
- *ls -a* to view hidden files in the current directory

Most of these commands are demonstrated in the following screenshots:
<img width="994" alt="Screen Shot 2023-01-12 at 3 15 36 PM" src="https://user-images.githubusercontent.com/69327109/212201333-2db579a2-29fb-412c-840f-f88ff8d5e69f.png">
<img width="706" alt="Screen Shot 2023-01-12 at 2 44 20 PM" src="https://user-images.githubusercontent.com/69327109/212197305-1b03fe90-4ed8-438a-b78f-046e6e3d8fda.png">
