
# 1.Installing VScode

Go to the VS code [website]( https://code.visualstudio.com/) and follow the instruction to download the VScode on your desktop. When you finish installing, the window of VScode should look like below: 
![Image](VS.png)

# 2.Remotely Connecting 
If you are a window user, please download [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)
Then, look up your personal course account for CSE15L on this [link](https://sdacs.ucsd.edu/~icc/index.php)

Once you find your account, open the terminal in VSCode and type $ssh cs15lwi22(your_special_pin)@ieng6.ucsd.edu. 
Type yes when you see the message that says the account can't be established, then give your password. You will see this message after login. 

![Image](Login.png)

# 3.Trying Some Commands
Try to type some command such as 
* `cd ~`
* `cd`
* `ls -lat`
* `ls -a`
* `ls <directory> where <directory> is /home linux/ieng6/cs15lwi22/cs15lwi22abc, where the abc is one of the other group members’ username`
* `cp /home/linux/ieng6/cs15lwi22/public/hello.txt ~/`
* `cat /home/linux/ieng6/cs15lwi22/public/hello.txt`

For example you will see something like this: 
![Image](cmd.png)

# 4.Moving Files with scp
Make a 

# 5.Setting an SSH Key

# 6.Optimizing Remote Running
