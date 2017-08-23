
# Arcanist installer for windows
> **Arcanist make file to be used with Inno Setup Compiler**

## Configuring default text editor
To configure the text editor that arcanist will use with commands like arc diff, please follow the instructions at https://secure.phabricator.com/book/phabricator/article/arcanist_windows/#configuring-an-editor

## Dependencies
+ Inno Setup Compiler
  + This repository is essentially a makefile for arcanist and its dependencies (PHP & libphutil)
  + Inno will be used to load the makefile and run the installation
  + Download the 'QuickStart Pack' from http://www.jrsoftware.org/isdl.php
+ Git
  + Git CLI will be used to clone this repo and pull down the submodules (libphutil and arcanist) prior to installation

## Arcanist Installation Instructions
1. Use git to clone this repository into a folder of your choice.
```sh
$ git clone https://github.com/paladox/Arcanist-installer-for-windows.git
```
2. Inside of the repository folder, run the following git commands
```sh
$ git submodule
$ git submodule update --init
```
3. Run Inno Setup Compiler (see Dependencies)
4. Use Inno to load the Arcanist.iss file inside of the repo folder
5. Run the script to start the installation process
    * *You can also compile the ```setup.exe``` file, which will save to the ```/out``` folder of the repo*
6. Install by navigating the installation wizard (Be sure to install PHP if you don't have it already)
7. Reboot (for good measure)
8. From a terminal type ```arc help``` to see if arc command is recognized and the arcanist help menu is displayed
    * *also ```php -v``` to make sure php is working*

## Troubleshooting Installation
+ In your windows environment variables, make sure your PATH system variable has paths to arcanist and php
  + make sure those paths are accurate
+ make sure you installed the submodules from the git repo before installation via Inno


## Notes
If you are using Cygwin on windows without having installed php for cygwin, the arc command will not work correctly.  It tries to call php on a filepath which is cygwin-specific i.e. /c/Users/myname/Documents instead of C:/Users/myname/Documents
Therefore, you will have to add an alias to your cygwin bash profile
```sh
alias arc='php C:/path/to/Arcanist/arcanist/scripts/arcanist.php'
```

## TODO
Add check for php to make sure php is installed otherwise download it and either get the user to unzip it or unzip it with the installer and add to environmental path variable.
