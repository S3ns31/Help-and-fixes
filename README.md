# Help-and-fixes
linux fixes 

handy commands will follow sooner or later 

{I} fixing your anonsurf {I}

after updating upgrading or full dist-upgrades 
it can be that your proxys like anonsurf aint working properly 

to fo fix it use this 

-* apt-get purge anonsurf 
-* apt-get autoremove 

-* git clone https://github.com/ParrotSec/anonsurf

-* cd anonsurf 

-* make install



%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%    basic linux commands 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

here we present a list of most used linux stuff 

%%%%%%%%%%%%%%%%%%%%%
unmet depency fixes %
%%%%%%%%%%%%%%%%%%%%%

    sudo apt-get -f install
     
    sudo apt-get upgrade --fix-missing
     
    sudo apt-get upgrade --fix-broken

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%nano cheat sheet: keyboard shortcuts
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

CtrlX: Exit the editor. If you've edited text without saving, you'll be prompted as to whether you really want to exit.

CtrlO: Write (output) the current contents of the text buffer to a file. A filename prompt will appear; press CtrlT to open the file navigator shown above.

CtrlR: Read a text file into the current editing session. At the filename prompt, hit CtrlT for the file navigator.

CtrlK: Cut a line into the clipboard. You can press this repeatedly to copy multiple lines, which are then stored as one chunk.

CtrlJ: Justify (fill out) a paragraph of text. By default, this reflows text to match the width of the editing window.

CtrlU: Uncut text, or rather, paste it from the clipboard. Note that after a Justify operation, this turns into unjustify.

CtrlT: Check spelling.

CtrlW: Find a word or phrase. At the prompt, use the cursor keys to go through previous search terms, or hit CtrlR to move into replace mode. Alternatively you can hit CtrlT to go to a specific line.

CtrlC: Show current line number and file information.

CtrlG: Get help; this provides information on navigating through files and common keyboard commands.

------------------------------------------------------------------------------------------------------------------
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%SCREEN LOCKER 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
if screen appears use ctrl+alt+f2
login with root 

use command loginctl unlock-sessions

then switch back ctrl+alt+f7

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%    su commmands 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
su for  | > parrot and debian
sudo su | > for ubuntu/xubuntu 
sudo    | >
yum     | > Fedora arch  centos 

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%        ssh
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
ssh @ip
ssh user@ip 
ssh user@ip -p portnumber

#transfer files to server or system

scp -r  file  user@ip:/home/user/Desktop

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%     remove files 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
rm -f file 
rm -r folder 
rm file 

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%      copy files 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
cp /file/  /home/user/filedestination/

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%find processes thats runing 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
ps aux 
ps aux | grep file.py 
ps aux | grep file.pl
ps aux | grep program name 

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
#    kill processes 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
kill -kill process id 
kill -kill progname 

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%        npm 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
npm install package-name
npm rebuild package-name 

npm install -g  raw-socket

npm install -g package-name  --unsafe-perm

%%%%%%%%%%%%%%%%%%%%%%%
%Fixing npm permissions
%%%%%%%%%%%%%%%%%%%%%%%

Fixing npm permissions

You may receive an EACCES error when you try to install a package globally. This indicates that you do not have permission to write to the directories that npm uses to store global packages and commands.

You can fix this problem using one of three options:

    Change the permission to npm's default directory.
    Change npm's default directory to another directory.
    Install node with a package manager that takes care of this for you.

You should back-up your computer before moving forward.
Option 1: Change the permission to npm's default directory

    Find the path to npm's directory:

     npm config get prefix

    For many systems, this will be /usr/local.

        WARNING: If the displayed path is just /usr, switch to Option 2 or you will mess up your permissions.

    Change the owner of npm's directories to the name of the current user (your username!):

     sudo chown -R $(whoami) $(npm config get prefix)/{lib/node_modules,bin,share}

    This changes the permissions of the sub-folders used by npm and some other tools (lib/node_modules, bin, and share).

Option 2: Change npm's default directory to another directory

There are times when you do not want to change ownership of the default directory that npm uses (i.e. /usr) as this could cause some problems, for example if you are sharing the system with other users.

Instead, you can configure npm to use a different directory altogether. In our case, this will be a hidden directory in our home folder.

    Make a directory for global installations:

     mkdir ~/.npm-global

    Configure npm to use the new directory path:

     npm config set prefix '~/.npm-global'

    Open or create a ~/.profile file and add this line:

     export PATH=~/.npm-global/bin:$PATH

    Back on the command line, update your system variables:

     source ~/.profile

Test: Download a package globally without using sudo.

    npm install -g jshint

Instead of steps 2-4 you can also use the corresponding ENV variable (e.g. if you don't want to modify ~/.profile):

    NPM_CONFIG_PREFIX=~/.npm-global

Option 3: Use a package manager that takes care of this for you.

If you're doing a fresh install of node on Mac OS you can avoid this problem altogether by using the Homebrew package manager. Homebrew sets things up out of the box with the correct permissions.

brew install node









######################################################
How to fix broken packages using the Command Line    #
######################################################

                _.--| LuLz|:                    
               <____|.----||                    
                      .---''---,                
   The                 ;..__..'    _...         
    Lulz            , '/  ||/..--''    \        
     Boat         ,'_ /'.-||            :       
      2016   _..-' ''/    ||  \    \   _|/|     
           \        /-._;/||   \    \,;'   \    
           ,\      /    /`||    \   //    `:`.  
         ,'  \    /-._;/  ||    : ::    ,.   . 
       ,'     \  /    /`-.||    | || ' :  `.`.)
    _,'        |;._: /|  ;||    | `|   :    `' 
  ,'   `.      /    /`-:_/||    |  |  : \      
  `--.   )    /'-._/    /:||       |   \ \     
     /  /    /'_  /;`-./_;||__..--';    : :    
    /  (    /  -./_  _/  .||'o |   /     ' |    
   /  , \._/_/_./--''/_  /||___|_,'      | |    
  :  /   `'-'--'----'---------'          / |    
  | :     O ._O   O_. O ._O   O_.       ; ;    
  : `.      //    //    //    //       /     
~~~`.______//____//____//____//_______ ,'~~     
          //    //~   //    // ~ ~ ~ ~~~~    
   ~~   _//   _//   _// ~ _//    ~  ~ ~ ~    
 ~     / /   / /   / /   / /  ~      ~~       
      ~~~   ~~~   ~~~   ~~~                   
                                   Setting Sail to the horizon. 
                                              Yours 
                                        lulzSecurity2016
                                           % |\| |\| %


#################################################################################################################################################################################################

Using aptitude for package management instead of apt-get, please note that it is bad practice to use aptitude and apt-get interchangeably, as they record separately the changes made by a user.

 

Open the Terminal from the Mint Menu and start with the commands:

-* sudo aptitude update && sudo aptitude install gtkorphan

The && is used to run the second command if the first command runs successfully.

 

Continue by running:

-* sudo aptitude update && sudo aptitude upgrade

This is used to double-check that you have all the updates.

 

To clear out the broken packages use the command:

-* sudo aptitude -f
-* su apt-get -f (debian based )

It brings up a beautiful interface to search, navigate, install, update and otherwise to manage packages.

Use the commands on the screen to install all the updates. You may use the mouse or CTRL + T to open the menu. Also, you could use the arrow keys and the Enter key to navigate.

You can also install the Aptitude Package Manager if you want to use something like Synaptic. 
Just type aptitude-gtk in the search field of the Mint Menu and click on Install package 'aptitude-gtk'. You can then find it under the Administration menu.

 You may also use other commands to:

    install software for your system, with needed dependencies as well:

-* sudo aptitude install
-* su apt-get install (debian based )

    remove packages as well as orphaned dependencies:

-* sudo aptitude remove
-* su apt-get remove (debian based )

    remove packages and orphaned dependencies, as well as any configuration files left behind:   

-* sudo aptitude purge
-* su apt-get purge (debian based )

    search for packages in the local apt package lists:

-* sudo aptitude search package-name
-* su apt-get search package-name (debian based )

    show details about a package:

-* sudo aptitude show package-name
-* su apt-get show package-name (debian based )

    update the local packages lists:

-* sudo aptitude update
-* su apt-get update (debian based )

    upgrade any installed packages that have been updated:

-* sudo aptitude upgrade
-* su apt-get upgrade (debian based )

    upgrade packages, even if it means uninstalling certain packages:

-* sudo aptitude dist-upgrade
-* su apt-get dist-upgrade (debain  based "solves most issues")

    delete only out-of-date packages, but keep current ones:

-* sudo aptitude autoclean
-* su apt-get autoclean (debain based )

    delete any downloaded files necessary for installing the software on your system:

-* sudo aptitude clean
-* su apt-get clean (debian based )

    fix a package at it’s current version, and don’t update it:

-* sudo aptitude hold
-* su apt-get hold (debian based )

The wind is breezy, the sun is setting and we sail for the horizon.

Yours 

Lulz Security 2016 team
 % |\||\| %
