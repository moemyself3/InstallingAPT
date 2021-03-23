# Installing APT

Here are several lines you can copy and paste into terminal when installing APT according to the video:


Verify if Java is installed in Terminal

    java -version

---

Look for the configuration file `.bash_profile` or `.profile`

    ls -la | grep '.bash\|.profile'
        
---

If you don't have either `.bash_profile` or `.profile` make one by using

    touch .bash_profile

---

If you have or had to make `.bash_profile` use 

    echo "export APT_HOME=~/Downloads/APT_v2.8.4
    export PATH=\$PATH:\$APT_HOME
    export APT_ARCH=MAC" >> .bash_profile

---

If not and you have `.profile` use

    echo "export APT_HOME=~/Downloads/APT_v2.8.4
    export PATH=\$PATH:\$APT_HOME
    export APT_ARCH=MAC" >> .profile

