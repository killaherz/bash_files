# Bash files

This is my bash files Project for Linux which should also work on Mac OS X.
It mainly grew out of the tweaks and additions I applied for my personal use.

Some inspiration was taken from projects such as [oh-my-zsh
](https://github.com/robbyrussell/oh-my-zsh/tree/master/lib), [bash-it](https://github.com/revans/bash-it) and others.

`Bash files` is a work in progress project, everything is still a bit quick and dirty and constantly moving. I hope you enjoy it nevertheless.

Feel free to contribute, reuse, clone, etc.

-binaryanomaly

<br>
---

### Screenshot
The current version (10.03.2015) looks like this:

![Bash_files welcome screen](http://i.imgur.com/zEKcdZk.png "Bash_files welcome screen")

<br>


### Updates - New features

##### 14.03.2015
 - Added public ip info

##### 10.03.2015
 - Added cpuinfo
 - Added raminfo

---

##### Feature list

 - Config vars for features
 - OS type detection support for Linux and OS X
 - Cross-platform robust checks

##### Info sections (configurable)
 - Hostname with figlets, lolcat supported
 - System info (kernel, architecture)
 - Cpu info
 - File system info
 - Last logins
 - Random bash comand info (whatis)
 - Reboot required check and message on welcome screen and/or in prompt

<br>


### Setup

Clone the repository into your home directory, it will create the `.bash_files` subdirectory:

```bash
git clone https://github.com/binaryanomaly/bash_files ~/.bash_files
```


#### Invoke init file from .bashrc (.bash_profile on Mac OS X)

Add the following at the end of your `.bashrc` or `.bash_profile` in your home directory:

```bash
# Bash_dotfiles initialization
if [ -f ~/.bash_files/init.sh ]; then
    . ~/.bash_files/init.sh
fi
```


#### Dependencies - Standard Linux commands used

- `dig` to determine the public ip via ipecho.net
- `free` for ram info
- `df` for diskspace info
- `last` for last logins
- `whatis` for command related infos


#### Additional packages that can optionally be installed

- `figlet` for big ascii letter hostname
- `lolcat` to colorize the ascii letter hostname

The script will autodetect if each of those is installed and disable the features if not found.

**Linux** (apt)
```bash
sudo apt-get install figlet lolcat
```

**OS X** (homebrew)
```
brew install figlet
gem install lolcat
```

<br>


### Directory and file structure

The project lives in `~/.bash_files/` 

| Directory | Description |
| ---- | ----------- |
| aliases/  | Directory for alias definitions - `*aliases.sh` gets sourced |
| config/  | Directory for config files - `*config.sh` gets sourced |
| lib/ | Directory where base functionality is stored - `base*.sh` gets sourced |

<br>


| File | Description |
| ---- | ----------- |
| init.sh  | Init file that sources all the other dirs/files |

<br>

### Conventions

 - Use `bf_` prefix for variable names