# Installing Aperture Photometry Tool - APT 🔭

###### Note: These instructions are for Aperture Photometry Tool. As far as I know, this APT does not come with super cow powers.

Here are several lines you can copy and paste into terminal when installing APT according to the video:
* How To Install APT all macOS: https://youtu.be/79Ja3AG8tYI
* _(Old version)_ How To Install APT macOS using Legacy Java: https://youtu.be/yU04ynNJXS0

## Step 0. Download APT to the Downloads folder

You can download the from APT website (https://aperturephotometry.org/downloads/).

-or-

You can right click, then select Save target as or Save link as or Download linked file:

* For version 3.0.2: http://web.ipac.caltech.edu/staff/laher/apt/APT_v3.0.2.tar.gz
* For version 2.8.4: http://web.ipac.caltech.edu/staff/laher/apt/APT_v2.8.4.tar.gz

Once you have downloaded the file make sure to place it in the Downloads folder.

>If using version 2.8.4 replace `APT_v3.0.2.tar.gz` with `APT_v2.8.4.tar.gz` in the instructions throughout this guide.

Open Finder and double click `APT_v3.0.2.tar.gz`. 
Once you can confirm you have the normal folder named `APT_v3.0.2` delete the file named `APT_v3.0.2.tar.gz`

Close Finder

## Step 1. Verify if you have java installed
Verify if Java is installed in Terminal

Copy and paste this into Terminal:

    java -version
    
If you do not have Java installed, visit the following website, download, and install java:
https://java.com/en/download/

---

## Step 2. Verify what shell interpreter you are using
The shell interpreter will load a different configuration file depending on which version you are using.

Copy and Paste this into Terminal:

    echo $0

For this tutorial we will only cover the cases for the following outputs of the previous command:

    -bash
    -zsh

---

## Step 3 for zsh. Check for the configuration file
Look for the configuration file `.zprofile`

Copy and Paste this into Terminal:

    ls -la | grep '.z'
    
If you don't have `.zprofile` make one.
Copy and Paste this into Terminal:

    touch .zprofile

Now run the following to add APT in your configuration file.
Copy and Paste this into Terminal:

    echo "export APT_HOME=~/Downloads/APT_v3.0.2
    export PATH=\$PATH:\$APT_HOME
    export APT_ARCH=MAC" >> .zprofile

Close Terminal 

---

## Step 3 for bash. Check for the configuration files
Look for the configuration file `.bash_profile` and `.profile`
Copy and Paste this into Terminal:

    ls -la | grep '.bash\|.profile'

If you don't have either `.bash_profile` or `.profile` make one
Copy and Paste this into Terminal:

    touch .bash_profile


If you have or had to make `.bash_profile`
Copy and Paste this into Terminal:

    echo "export APT_HOME=~/Downloads/APT_v3.0.2
    export PATH=\$PATH:\$APT_HOME
    export APT_ARCH=MAC" >> .bash_profile


If not and you have `.profile`
Copy and Paste this into Terminal:

    echo "export APT_HOME=~/Downloads/APT_v3.0.2
    export PATH=\$PATH:\$APT_HOME
    export APT_ARCH=MAC" >> .profile
    
Close Terminal 

---

## Step 4. Running APT

1. Open Terminal
2. Type AP
3. Hit the tab key, it should auto complete to say `APT.csh`
4. Hit Enter
5. It should open right away!

---

## Notes About Running APT
Since we are using terminal to run APT, it needs to remain open while you use APT.

## Closing APT

1. Close the APT window.
2. You may now close terminal.

---

# Uninstalling APT
If you followed the instructions from this guide, then you are running the files directly from the Downloads folder when you run APT.csh in terminal. There is nothing actually distributed in your machine. Uninstalling is deleting the APT files and Cleaning up the config file.

## 1. Delete Files
To uninstall APT you would just need to delete the folder APT_v3.0.2.

## 2. Clean Config Files
To clean the `.profile`, `.bash_profile`, or `.zprofile` (depending on the interpreter you are using `bash` or `zsh`) you will need to open the corresponding file and delete the lines we added in Step 3 for your interpreter.  

If you want to clean the configuration file first identify which one you did. For my example, I will use `.zprofile`. You can replace `.zprofile` with `.profile` or `.bash_profile` where ever needed in the following instructions. 

### Peek at the configuration file
First verify that you actually have the things related to APT by checking the file in terminal by copy and pasting the following:

```
cat .zprofile
```

You should see somewhere in the output the following:
```
export APT_HOME=~/Downloads/APT_v3.0.2
export PATH=$PATH:$APT_HOME
export APT_ARCH=MAC
```
### Delete the lines in the config file
Without using an editor I do not know of an easier way other than doing this step for each line one at a time using the following in terminal and hitting enter between each:

```
sed -i '' '/export APT_HOME=~\/Downloads\/APT_v3.0.2/d' .zprofile
```

```
sed -i '' '/export PATH=$PATH:$APT_HOME/d' .zprofile
```

```
sed -i '' '/export APT_ARCH=MAC/d' .zprofile
```

Then you can check to see if it worked by using:

```
cat .zprofile
```

You should no longer see the lines related to APT!


