# Shell-Customization-Memento

Let's see some customization for our Linux shell !

## Environment variables

Environment variables are dynamic variables used by process of the OS, they are used to allow communication between programs.  
For instance your environment varibale **HOME** should have value **/home/username**.

### Usefull commands

Here are some usefull commands for bash shells.

#### See environment variables

- show all environment variables :  
`printenv`  
`env`

- show value of one variable :  
`printenv VARIABLE`  
`echo $VARIABLE`

#### Temporarily manipulate environment variables

Here we can add, change and delete value of variables.

- Add value of one variable :  
`VARIABLE=value`

- Change value of one variable :  
`VARIABLE=newValue`

- Delete value of one variable :  
`VARIABLE=`

- Add environment variables that doesn't exist :
`export VARIABLE`  
`export VARIABLE=value`

- Delete environment variable :  
`unset VARIABLE`  
`export -n VARIABLE` (Delete the status of environment varibale beut still exists as a simple bash variable)

#### Permanent environment variables

To keep the changes of our environment variables we can save them in some script files located in our home repertory.

#### User session

- **~/.bashrc** : not the best one because it will receate all the variables every time we open a terminal.
- **~/.profile** : best one because it will be exceuted once at the lauch of the graphical session or console mode.

#### Sytem wide

- **/etc/bash.bashrc** :not the best one executed only for the specific shell.
- **/etc/profile** : executed while starting any session in console mode.
- **/etc/environment** : best one, specially used for new variables.

### Commun variable environment

| VARIABLE | Description                                                  |
| -------- | ------------------------------------------------------------ |
| USER     | Current logged in user                                       |
| HOME     | Home directory of the current user                           |
| EDITOR   | Default file editor to be used                               |
| SHELL    | Path of the current user’s shell                             |
| LOGNAME  | Name of the current user                                     |
| PATH     | A list of directories to be searched when executing commands |
| LANG     | Current locales settings                                     |
| TERM     | Current terminal emulation                                   |

## Aliases

A shell alias is a shortcut for a command or some commands. It is used to avoid typing long commands repititively or incorrect commands.

To set a alias =, we have to type in this format :  
`alias name='command'`  
or `alias name="command"`

In order to save it we could save it to our **.bashrc** file :  
`echo "alias name='command' >> ~/.bashrc`

After creating the alias, we have to reload the bash configuration :
`. ~/.bashrc`

### Some useful aliases

alias upgrade='sudo apt update && sudo apt upgrade'
alias install='sudo apt update && sudo apt install'
alias reloadbash='. ~/.bashrc'
alias ll='ls -la'
alias l.='ls -ld .* --color=auto'
alias editbash='vim $HOME/.bashrc'
alias svi='sudo vim'
alias vi='vim'
alias ports='netstat -tulanp'
alias rm='rm -I --preserve-root'
alias mv='mv -i'
alias cp='cp -i'
alias ln='ln -i'
alias su='sudo -i'
alias autoremove='sudo apt autoremove && sudo apt autoclean'
alias uninstall='sudo apt remove'

## Show some text at the log in

### issue

To show some message before we log in our session, we can modify **/etc/issue** file. It will diplsay the content beofre the log in prompt.

### MOTD

To show a message after the log in prompt, we can modify the **/etc/motd** file. Motd stands for **M**essage **O**f **T**he **D**ay, each time the user logs in, the contents of the/ETC/MOTD file are displayed in the user's terminal. The system administrator can edit the system activity message in the file, for example: The administrator notifies the user when the system is upgrading the software or hardware, when the system is maintained, and so on.

Plus, we can execute some commands for the motd, we jsut have to modify the **/etc/update-motd.d/scriptname** file.

Here is a usefull web site to generate ASCCI art fot hte motd :

[ASSCI Maker](https://patorjk.com/software/taag/#p=display&f=Graffiti&t=Type%20Something%20)

## The prompt

OUr commuun prompt should look something like this :  
username@hostname:~$

Last but not least, now we are going to customize our prompt.

The environment PS1 is our main prompt, it is the text printed before each command.
> PS2 is for printing more input
> PS3 for select menu 
> PS4 for debugging

To edit your prompt you can add this at the end of our **./bashrc** file :
`PS1=specialCharacters/commands/whateverWeWant`

Here are some special characters :

\a – A bell character  
\d – Date (day/month/date)  
\D{format} – Use this to call the system to respond with the current time  
\e – Escape character  
\h – Hostname (short)  
\H – Full hostname (domain name)  
\j – Number of jobs being managed by the shell  
\l – The basename of the shells terminal device  
\n – New line  
\r – Carriage return  
\s – The name of the shell  
\t – Time (hour:minute:second)  
\@ – Time, 12-hour AM/PM  
\A – Time, 24-hour, without seconds  
\u – Current username  
\v – BASH version  
\V – Extra information about the BASH version  
\w – Current working directory (\$HOME is represented by ~)  
\W – The basename of the working directory (\$HOME is represented by ~)  
\\\! – Lists this command’s number in the history  
\\# – This command’s command number  
\\$ – Specifies whether the user is root (#) or otherwise ($)  
\\\ – Backslash  
\\[ – Start a sequence of non-displayed characters (useful if you want to add a command or instruction set to the prompt)  
\\] – Close or end a sequence of non-displayed characters  

Here is a usefull web site to generate our custom prompt :

[ezprompt](http://ezprompt.net/)

___
Author : AnthonyF
