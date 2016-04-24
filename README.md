# Arcanist installer for windows
This is a windows installer to install Arcanist for windows

Configuring your editor
======

To configure your editor that arcanist will use for things like arc diff please follow the instructions at https://secure.phabricator.com/book/phabricator/article/arcanist_windows/#configuring-an-editor

Help make installer better
======

To help with making the install better by making an installer please download from http://www.jrsoftware.org/isdl.php and select QuickStart Pack please.

Then just download the files from here and do git submodule git submodule update --init and then open up the .iss file in the inno setup script studio.

TODO
====

Add check for php to make sure php is installed otherwise download it and either get the user to unzip it or unzip it with the installer and add to enviromental path variable.
