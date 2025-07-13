# multi-dir-file-chmod
How to recursively set 755 for directories and 644 for files in Linux

Use find and chmod command to execute in one inline command.

e.g:
* Directories will be set to 770
* Files will be set to 660

## Command example: ##

find /DIRECTORY/ -type d -exec chmod 755 {} + -o -type f -exec chmod 644 {} +

## ##


Break down of this command:

find .: This starts the search in the current directory (.) and its subdirectories.

-type d: This option tells find to only consider directories.

-exec chmod 770 {} +: For every directory found, execute chmod 770. The {} is a placeholder for the found directory name, and + is a more efficient way to pass multiple arguments to chmod at once (rather than running chmod for each individual directory).

-o: This is the logical OR operator. It means if the previous condition (-type d) is false, then try the next condition.

-type f: This option tells find to only consider regular files.

-exec chmod 660 {} +: For every file found, execute chmod 660. Similar to the directory part, {} is a placeholder for the file name, and + passes multiple arguments to chmod.

This command effectively processes all directories and then all files in one go, setting their respective permissions.










