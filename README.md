![pgAdmin](image.png)  

# pgAdmin 4 Desktop Mode in Ubuntu

## Versions

Python: 3.6.7  
OS: Ubuntu 18.04.1 LTS  

## Install dependencies, create virtual environment, download and install

```
sudo apt-get install virtualenv python3-pip libpq-dev python3-dev

cd
virtualenv -p python3 pgadmin4
cd pgadmin4
source bin/activate

pip3 install https://ftp.postgresql.org/pub/pgadmin/pgadmin4/v3.6/pip/pgadmin4-3.6-py2.py3-none-any.whl
```
## Configure
```
nano lib/python3.6/site-packages/pgadmin4/config_local.py
```
Write:
```
import os
DATA_DIR = os.path.realpath(os.path.expanduser(u'~/.pgadmin/'))
LOG_FILE = os.path.join(DATA_DIR, 'pgadmin4.log')
SQLITE_PATH = os.path.join(DATA_DIR, 'pgadmin4.db')
SESSION_DB_PATH = os.path.join(DATA_DIR, 'sessions')
STORAGE_DIR = os.path.join(DATA_DIR, 'storage')
SERVER_MODE = False
```

## Run pgAdmin 4

```
cd ~/pgadmin4
source bin/activate
python3 lib/python3.6/site-packages/pgadmin4/pgAdmin4.py
```

Go to [http://127.0.0.1:5050/browser/][baacb4b8]

  [baacb4b8]: http://127.0.0.1:5050/browser/ "http://127.0.0.1:5050/browser/"

## Useful links

[Download page][f29d5a51]

  [f29d5a51]: https://www.pgadmin.org/download/pgadmin-4-python-wheel/ "Download page"

[Askubuntu post][31882bab]

  [31882bab]: https://askubuntu.com/questions/831262/how-to-install-pgadmin-4-in-desktop-mode-on-ubuntu "askubuntu"
