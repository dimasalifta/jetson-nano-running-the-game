# Documentation Running the Game on Jetson Nano
## A. Setup for PC Remote
1. Downloads & Install VNC Viewer

    Link Downloads https://www.realvnc.com/en/connect/download/viewer

2. Open  & Setup VNC Viewer
   
   File $\rightarrow$ New Connection $\rightarrow$ Input Game PC's IP

   ![img](/assets/images/picture1.png)

3. Connect to Game VNC, Password : **dewaticrobotic**

## B. Setup for Jetson Nano
### **1. When it is connected to Jetson Nano, the desktop page of jetson nano will appear as shown below**

   ![img](/assets/images/picture2.png)
   
### **2. We will run the game program using linux terminal**
   
   #### Open terminal using shortcut `Ctrl+Alt+T`

   ![img](/assets/images/picture3.png)
### **3. then, to run the program we have to move to the game directory by using commands**
   
   ##### *Note:*
   
   ##### `cd`: The cd command will allow you to change directories.

   ##### `ls`: The ls command will show you ('list') the files in your current directory.

   #### Now, we type the command 
```
cd Documents/
```
   #### Results:
   ![picture4](/assets/images/picture4.png)
   
   #### then, check if the game folder already exists using commands `ls`
```
ls
```
   #### Results:
   ![picture](/assets/images/picture5.png)
   #### from the results of the command above there are several game folders
   
   `game-m14` for Poker Dice
   
   `game-m6` for 24D Spin

   `game-p9` for 12D
   
   #### the following command to run the program 12D :
```
cd game-p9/
```
```
python3 p9-rev01.py
``` 
   #### Results:
   ![picture](/assets/images/picture6.png)

   #### Wait until it open successfully and show this windows
   ![picture](/assets/images/picture7.png)


