## Installing VSCode

To install VSCode, first go to <a href="https://code.visualstudio.com/download"> Visual Studio Code </a>. Select Windows/Mac based on what your computer is running on. Afterwards, follow the installer's directions, and wait a few minutes for VSCode to download. Double-click the VSCode icon to open it after it has finished installing on your machine. You will be prompted with a choice to either make a new project or open an existing folder. After opening a project on VSCode (I opened the starter code for CSE 12's first PA), your screen should look like this:
<img width="1127" alt="Screen Shot 2023-01-12 at 2 31 05 PM" src="https://user-images.githubusercontent.com/69327109/212196294-8c494886-eb7f-42ff-9aad-a8e8edf5a2aa.png">

## Remotely Connecting

To remotely connect to the CSE15L, enter the command ```ssh cs15lwi23auw@ieng6.ucsd.edu``` into your terminal, where cs15lwi23auw is replaced by your own username (in my case, cs15lwi23auw is my username). You will be prompted to enter your password, which you should have set beforehand (if you need to reset the password, visit <a href="https://support.ucsd.edu/its"> SDACS</a>. Afterwards, you should see the below message show on your terminal, which confirms that you've connected to the remote server.
<img width="1093" alt="Screen Shot 2023-01-28 at 12 55 15 PM" src="https://user-images.githubusercontent.com/69327109/215290735-0468673a-3f2f-4552-8b37-c616aee6807d.png">

## Trying out some commands

Once you are connected to the remote computer, you can execute commands on them and access their files. I tried general commands such as:
- ```cd``` to change directory
- ```pwd``` to see my current directory
- ```ls``` to list all files and folders in the current directory

As well as more specific ones such as:
- ```cat /home/linux/ieng6/cs15lwi23/public/hello.txt``` to print the contents of a file named **hello.txt**
- ```cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/``` to copy that same file
- ```ls -a``` to view hidden files in the current directory

Most of these commands are demonstrated in the following screenshots:
<img width="1218" alt="Screen Shot 2023-01-28 at 12 59 48 PM" src="https://user-images.githubusercontent.com/69327109/215290901-c9a22a9f-7ed3-4a2b-9a42-af16f30075a0.png">
<img width="1077" alt="Screen Shot 2023-01-28 at 1 00 13 PM" src="https://user-images.githubusercontent.com/69327109/215290906-8e698aa5-2284-409b-b103-d5c9dc33ba76.png">

<img width="706" alt="Screen Shot 2023-01-12 at 2 44 20 PM" src="https://user-images.githubusercontent.com/69327109/212197305-1b03fe90-4ed8-438a-b78f-046e6e3d8fda.png">

