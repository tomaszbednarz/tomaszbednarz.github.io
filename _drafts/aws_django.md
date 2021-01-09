

* Log in to AWS EC2 instance

* Update yum

```
sudo yum update
```

* Install Python3 

```
sudo install python3 -y
````

* Install newest version of SQLite3 required by Django

```
curl https://www.sqlite.org/2020/sqlite-autoconf-3320300.tar.gz | tar xzf -
cd sqlite-autoconf-3320300/
./configure 
make
sudo make install
```

* Add to ~/.bashrc for SQLite3 be visible within Python3

```
export LD_LIBRARY_PATH=/usr/local/lib
```

* Create venv

```
python3 -m venv my_app/env
source ~/my_app/env/bin/activate
pip install pip -upgrade
pip install django -y
```

* Add env

```
 echo "source ${HOME}/my_app/env/bin/activate" >> ${HOME}/.bashrc
 ```

 * Create django project

 ```
 mkdir iSME
 cd iSME
 django-admin startproject config .
 python manage.py migrate
 python manage.py runserver 0.0.0.0:8000
 ```

 * Remember to add port 8000 in AWS console to open traffic in Security tab
