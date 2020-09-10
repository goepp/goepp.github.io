
# Fixing broken package dependencies
https://linuxhint.com/apt_get_fix_missing_broken_packages/

Notes: 

- `sudo apt-get install -f` worked for me.
- The `Err:` messages from `sudo apt-get update` were fixed by commenting out the correponding source list lines in `/etc/apt/sources.list.d/`.
I made sure none of these packages corresponded to important software.
- The message `GPG pubkey missing` can be fixed by adding the pubkey to the *apt keyring*, using a command such as

`wget -qO - http://my.url.to/archive.key | sudo apt-key add -`

where `my.url.to/archive.key` it the repository's key's url.

- How to fix `Signature by key uses weak digest algorithm (SHA1°)`? According to https://askubuntu.com/questions/760796/how-to-fix-apt-signature-by-key-uses-weak-digest-algorithm-sha1, this must be fixed by the repository's owner. This does not prevent from using apt, it is just a warning.

# Installing python
- python-dev is the development version of python, which allows to build executables.
- [https://github.com/pyenv/pyenv](`pyenv`) is a tool that manages the different versions of python on a system .
- `sudo apt install python3.8-dev` installs the required version of python
- [https://linuxhint.com/update_alternatives_ubuntu/](`update-alternatives`) allows to choose what executable of python the commands `python` and `python2` point to.
One sets an *alternative* as follows:
`sudo update-alternatives --install /usr/local/bin/python python /usr/bin/python2 20`
One can see the alternatives for a command using `update-alternatives --query python`.

 
# Installing python packages
I need to install `watchdog`.
Try with a virtual environment: `python3 -m venv <venv_name>`.
Rather, I want to install watchdog for python3.8.
The command `/usr/bin/python3.8/ -m venv .` throws the error:

> Error: Command '['/home/vivien/postdoc/bin/python3.8', '-Im', 'ensurepip', '--upgrade', '--default-pip']' returned non-zero exit status 1.
>
and so did the command `python3.8 -m venv .`.

- How to install venv for a new version of python?
`sudo apt install python3.8-venv`
Then `python3.8 -m venv .` worked and created a virtual environment.

- How to install packages in this virtual environment?
`source bin/activate`
`pip install watchdog`
 
Then `python3.8 ~/.vim/bundle/YouCompleteMe/install.py --all`, which returns:
/home/vivien/venv3.8/bin/python3.8: can't open file 'setup.py': [Errno 2] No such file or directory
Failed to build watchdog module.

This is strange, since I can import watchdog form the python3.8 interpreter.

## Using pip
- How to select the executable for which the python packages will be installed?





