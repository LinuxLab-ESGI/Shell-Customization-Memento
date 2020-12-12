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

## 
Motd
site
Prompt
site