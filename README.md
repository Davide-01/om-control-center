om-control-center
===========

version: 1.0.0

This is the om-control-center for test

requires the following dependencies:

- python-qt4-webkit
- web.py http://webpy.org/
- bigbashview https://github.com/thor27/bigbashview/

bigbashview is integrated with scripts om-control-center as already into om-control-center

##### Installing Dependencies
to install python-qt4-webkit, we can use urpmi:
```sh
urpmi python-qt4-webkit
```

##### Installing web.py
* download the latest web.py build from GitHub (https://github.com/webpy/webpy)
* setup web.py with following command as root:
```sh
python setup.py install
``` 

or just use urpmi:
```sh
urpmi python-webpy
```

##### Directory Structures
your files are:
```
bigbashview.py
client.py
server.py
bbv/
    globals.py
    globals.pyc
    __init__.py
    __init__.pyc
    main.py
    main.pyc
    server/
    ui/
    img/
```

if you package it separately om-control-center requires changes to the running script.

##### Running om-control-center
you can run the om-control-center for debugging, with following command:
```sh
python bigbashview.py -s 870x520 -c -i /usr/share/icons/openmandriva.svg index.sh.htm 2> /dev/null;
```

#####translations
* inside the folder ```usr/share/om-control-center/ ```
* there is a file called translation, all texts om-control-center are it is from it that will 
* generate the translation files
* format it is as follows
```variavel=$"text that will be shown in the om-control-center"```

with the command
```sh
bash --dump-po-strings translation > om-control-center.pot
```

om-control-center.pot is the translation file.

the bigbashview uses html, css and js to create the layout, if you want to make any changes or improvements
just edit the files with the format. sh.htm, and style.css that is inside the css folder.
files with the. scripts are run that will be read as if they were running through the terminal.

to execute a command within the html files (sh.htm) using the following command:
```sh
$(command to be executed)
```

example: 
```
     $(lsb_release -d | cut -d":" -f2) #shows the name of the Linux distribution
```      
