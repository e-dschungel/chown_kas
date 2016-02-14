# chown_kas
This is a replacement for chown for the SSH shell of the german hoster [all-inkl.com](http://www.all-inkl.com).
It is implemented in Python and makes use of the KAS API (see http://kasapi.kasserver.com/dokumentation/phpdoc/index.html).
It is intended to be used on the SSH shell (available for plans >= "Premium")  of kasserver.com, other usages are not supported.

It can also be used as an example on how to use the KAS API in Python. 

## Installation
* Login via SSH
* Install pip (if not installed already)
 * symlink `/.local` to `/www/htdocs/USER/.local` to make it survive a de- and reactivation of SSH and the migratation to another server: `ln -s /www/htdocs/USER/.local /.local` (replace USER with your username)
 * `wget https://bootstrap.pypa.io/get-pip.py && python get-pip.py --user && rm get-pip.py`
 * add `export PATH=$PATH:/.local/bin` to the file `/www/htdocs/USER/user_bashrc` (create file if neccessary)
 * `source /.bashrc`
* `pip install --user suds-jurko`
* `git clone https://e-dschungel@github.com/e-dschungel/chown_kas.git`
* add `alias chown='/www/htdocs/USER/chown_kas/chown_kas.py'` to the file `/www/htdocs/USER/user_bashrc`
* `source /.bashrc`

##Usage
Type `chown user path` to change the owner of the path to the given user.
The user can be `phpuser` or your current KAS user (i.e. `w123456`).
Other users are not allowed.
You will be prompted for your KAS password to perform the change.

###Flags
|flag|description|
|---|---|
|`-R`, `--recursive`| change owner recursively|
|`--version`| show version information|
|`--help`|show help message|
