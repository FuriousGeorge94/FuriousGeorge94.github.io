

---
title: resources
---

# George's Notes: A Work in ***Progress***

---learn

* Resources:
    * The Linux Command line
    * SCIP
    * Eloquent Javascript
    * [ Learning Vimscript the hard way ](https://learnvimscriptthehardway.stevelosh.com/)
    * [ Pandoc users manual ](https://pandoc.org/MANUAL.html)
    * [ vim user manual ](http://vimdoc.sourceforge.net/htmldoc/usr_toc.html)

This is a paragraph. :)

Here is a worse paragraph :(


*HERE* *IS* A **fat** *GIRAFFE*

![giraffe](https://ae01.alicdn.com/kf/HTB1QWylaOHrK1Rjy0Flq6AsaFXa9.jpg)

[the best email is](www.gmail.com)


            ^
          (   )
        (       )
       (         )
        *(.) (.)*
          *   *
            v


autodidact???

*** learn git ***

* let's fucking learn shit *
* *BOOKS*:
    * read shader book
    * the linux command line

**** take course ****




GPG key ID: 4AEE18F83AFDEB23
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIEqxm0xiFilJS9skaHztEibosT9c8QTSn+vCaYPhNNGt geo_sthom@DESKTOP-H5SJ2GO

 geo.thom@gmail.com 69:f2:65:75:3c:66:f5:de:f0:37:c3:f2:51:9d:27:b5
(/home/geo_thom/.ssh/id_ed25519):

 *** CNTRL-C Important and ctr-d stops linux jobs ***


 Never do ** ctrl s **

 You can use multiiple commands in the shell using ;
 

---
title: linux
---


## linux
*  shell commands:
    *  ls
    *  pwd
    *  clear
    * cd
    *  cd ..
    * mkdir
    * mv (rename)
    * 2 crl sequences -- CNTRL-C, CNTRL-D
    * touch
    * which
    * alias
    * type + (alias) displays what alias is actually writing
    * \ + (alias) overides alias
    * clip.exe < (filename)   #should try and get xclip to work
    * whatis - displays a brief explanation of program
    * coreurils -- a menu with hyperlinks to GNU programs
    * cat - concatenate files
    * sort - sort lines of text
    * uniq - report or omit repeated lines
    * grep - print lines matching a pattern
    * wc - print newline, word, and byte counts for each file
    * head - output first part of file
    * tail - output last part of file
    * tee - read from standard input and write to standard output and files
    * file descriptor: 0 - stdin, 1 -std out, 2 - error
    * \> - redirects standard output **overrites or creates file**
    * \>\> - redirects standard output but appends to file
    * '#' + redirect - channels to files discriptor (ex: ls /~ 2> error.txt)
    * redirecting both stout and error - ls /~ > text.txt 2>&1 (older)
    * newer way to redirect both stdout and error - ls /~ &> text.txt
    * must redirect error last
    * bit bucket - /dev/null,  redirects get thrown away(like trash can)
    * cat + (file) - copies file into stdin
    * cat with no args waits for you to type, then Ctrl-d indicates eof
    * can redirect(<vor >) cat into a file(stdout) or command line(stdin)
    * | - *pipe operator* pipes stdout of one command into stdin of another
    * (command) | less-  displays output of command that creates stdout
    * \> - connects command with file
    * | - puts output of commandd to input of another
    * grep *pattern* [file...] - finds patterns in text files
    * filter - commands combined together with |
    * tee - reads stdin into file and stdout - ls ~ | tee t.txt | less
    * $ - indicates variables
    * command substitution - ls -l \$(which lynx)
    * history - shows comand history
    * can use ! + history# to repeat that command
    * basename - strips the full path of file down
    * uname - print system information
    * trap arg signals - execute command when a signal is recieved

* Commom signals:
  * SIGHUP  - value 1: signifies hangup
  * SIGINT  - value 2: signifies interupt from keyboard
  * SIGKILL - value 9: signifies kill signal (**Can't be stopped**)
  * SIGTERM - value 15: signifies termination signal
  * SIGSTOP - value 17,19,23: signifies stop the process

* Pocesses:
    * daemon programs - programs with no ui that run in background
    * when a program launches another -parent process prodces child process
    * CTRL-s supsends processes while CNTRL-q resumes them
    * Process related commands:
        * top - display tasks
        * jobs - diplay a list of active jobs
        * bg - Put job in background
        * fg - put job in foreground
        * kill- send signall to process
        * killall - kill processes by name
        * shutdown - reboot or shutdown system
        * ps - prints snapshot of processes currently running
            * x - prints all processes regardless of terminal controlled by
            * aux - more info than x

* Shell Variables:
    * \$# - variable that stores the number of arguments
    * \$@ - variable that stores the paramaters that were passed
    * \$? - variable that stores the last success code
    * \$\$ - varibale that stores the proccess id (pid) of a program

* Permissions
    * chmod u=wrx,go= (file) - changes permisions so you can only run it

* Control Operators:
    * command1 && command2 - command2 executed if command1 returns status 0
    * command1 || command2 - command2 executed if command1 returns nonzero status

* Temporary Files:
    * use TEMP_FILE=\$TEMP_DIR/(program name).\$\$.\$RANDOM to name your temporary files

* Simple Variable cutting:
    
    ```
    var="apple orange"

    # This command will print 'apple'
    echo "$var%% *}"

    # This command will print 'orange'
    echo "${var##* }


    ```





 | Owner | Group | World |
 |------ |-------|-------|
 |   wrx |   wrx |   wrx |



| Octal | Binary | File Mode |
|:-----:|:------:|:---------:|
|   0   |   000  |    ---    |
|   1   |   001  |    --x    |
|   2   |   010  |    -w-    |
|   3   |   011  |    -wx    |
|   4   |   100  |    r--    |
|   5   |   101  |    r-x    |
|   6   |   110  |    rw-    |
|   7   |   111  |    rwx    |


---
title: bash
---


## bash if, for while, and case statements


```sh

if [[ ]]  #double brackets for bash single for sh
then

  body

fi

----------------

while [[ ]]
do

  body

done

-----------------

for i in {range}
do

  body

done


----------------

case word in

  [[:lower:]] | [[:upper:]] ) echo "you typed a letter"

  [0-9] )                     echo "you typed a digit"

  * )                         echo "you typed anythings else"

esac


----------------

until [ CONDITION ]
do


  body

done

```

## bash Error Exit Function


```sh


# An error exit function

PROGNAME=$(basename $0)

error_exit()
{
 # argument is string description of error


  echo "${PROGNAME}: ${1:-"Unknown Error")" 1>&2
  exit 1
}

# Using error_exit

if cd $some_directory; then
  rm *
else
  error_exit "$LINENO:Cannot change directory!  Aborting."
fi

# Implementation using || operator

command || error_exit "error message"

```


## Example of a cleanup function and using trap



```sh

# Program to print a text file with headers and footers

TEMP_FILE=/tmp/printfile.txt

clean_up() {

  # Perform program exit housekeeping
  rm $TEMP_FILE
  exit
}

trap clean_up SIGHUP SIGINT SIGTERM

pr $1 > $TEMP_FILE

echo -n "Print file? [y/n]: "
read
if [ "$REPLY" = "y" ]; then
  lpr $TEMP_FILE
fi
clean_up


```

## Example of shift to increment parameters

```sh



echo "You start with $# positional parameters"

 # Loop until all parameters are used up
  while [ "$1" != "" ]; do
       echo "Parameter 1 equals $1"
            echo "You now have $# positional parameters"

                 # Shift all the parameters down by one
                      shift

                       done

```

---
title: git
---


## git
  * ssh
  * ~/.gitconfig
  * git remote add git@gitlab.com:snapplesauce/eightball.git

---
title: vim
---


## Vim

* commands:
    * To change every occurrence of a character string between two lines,
        * :#,#s/old/new/g    where #,# are the line numbers of the range of lines where the substitution is to be done.
        * :%s/old/new/g      to change every occurrence in the whole file.
        * :%s/old/new/gc     to find every occurrence in the whole file, with a prompt whether to substitute or not.
        * use /< and /> to match the beginning and end of a word
        * gf - find and edit file under cursor

        ```
        Examples:
        :s/a\|b/xxx\0xxx/g		 modifies "a b"	     to "xxxaxxx xxxbxxx"
        :s/\([abc]\)\([efg]\)/\2\1/g	 modifies "af fa bg" to "fa fa gb"
        :s/abcde/abc^Mde/		 modifies "abcde"    to "abc", "de" (two lines)
        :s/$/\^M/			 modifies "abcde"    to "abcde^M"
        :s/\w\+/\u\0/g		 modifies "bla bla"  to "Bla Bla"

        ```
    * tab commands
        *  LtL - nex tab
        *  Ltn - new tab
    * i (insert)
    * motion  D - Deletes line
    *  set nohlsearch same thing but permanent
    * *. in command mode repeats last command*
    * :so % - restarts vimrc file without having to close+reopen
    * m + (character) - set mark in file
    * backtick + mark charcter jumps to that file at that location
    * f & t - jump to character on line. f at the char, t before char
    * <s-*> - in normal mode searches for the word under cursor
    * <c-w>[w, -, +, etc..] - key for manipulating windows
    * :next/:previous - moving between open vi files

* Settings:
    * set nu - nonu -- line numbers
    * :noh turns of highlighting until the next search

* Mapping:
    * nunmap - defaults a keymap
    * *always* use the noremap version of the commands
    * onoremap - used for movement remaps

* Text Objects
    * iw => "inner word"(works from anywhere in a word)
    * it => "inner taf"(the contents of an HTML tag)
    * i" => "inner quotes"
    * ip => "inner paragraph"
    * as => "a sentence"

---
title: regex
---

## Regular expressions:

    * \* - matches any charcter(and number?)




```
          # Example Regex

              \([^,]*\), \(.*\)

  The first part between \( \) matches "Last"	\(     \)
      match anything but a comma			        [^,]
      any number of times				              *
  matches ", " literally					            ,
  The second part between \( \) matches "First"		   \(  \)
      any character					            .
      any number of times					      *
```

>\\wsl$  - how to access linux in explorer

>curl + url > (new file name)  --- then -> chmod +x (file name) ix



>alias g=’git’ alias st=’git status’ alias com=’git commit -m’ alias clone=’git clone’
 alias sth=’git stash alias lg=’git log’alias u=’git add -u’ alias allias=’git add .’

>how to access c drive: cd /mnt/c

---
title: godot
---


## **Godot Global(singleton) function  -place in project settings:**


```

     func instance_node(node, location, parent):
         var node_instance = node.instance()

                parent.add_child(node_instance)
                    node_instance.global_position = location

                            return node_instance
```


---
title: pandoc
---




## Pandoc:
    * pandoc -o -s --template=<template path> <file name>.html  <file name of file to convert>
    * then use command preview while in directory and a webpage should pop up
    * \#\# my header {#foo}


---
title: json
---



## Javascript Object Notation

Here is an example of JSON:

```json

{
  "age": 25,
  "name":"George"
  "interests": [
  "linux"
  "Indie rock"
  "hipster girls"
  ]
}
```














