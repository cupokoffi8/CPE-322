# **Lab 4**
## *Install Necessary Libraries*
 ```ssh
$ pip3 -V
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Pip3-V.png)

 ```ssh
$ pip3 list
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Pip3List.png)

 ```ssh
$ sudo pip3 install -U setuptools
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/InstallSetuptools.png)

 ```ssh
$ sudo pip3 install -U django
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/InstallDjango.png)

 ```ssh
$ sudo pip3 install -U djangorestframework
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/InstallDjangorestframework.png)

 ```ssh
$ sudo pip3 install -U djangorestframework
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/InstallDjangorestframework.png)

 ```ssh
 $ sudo pip3 install -U django-filter 
 ``` 
 ![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/InstallDjangofilter.png)
 
  ```ssh
$ sudo pip3 install -U markdown
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/InstallMarkdown.png)

  ```ssh
$ sudo pip3 install -U requests
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/InstallRequests.png)

## *Install MariaDB Server and Client on Raspberry Pi*

  ```ssh
$ sudo apt update
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Update.png)

  ```ssh
$ sudo apt install mariadb-server mariadb-client
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/MariaDB/MariaDB1.png)
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/MariaDB/MariaDB2.png)
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/MariaDB/MariaDB3.png)

  ```ssh
$ sudo apt install python3-mysqldb
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/InstallMySQLdb.png)

  ```ssh
$ sudo pip3 install -U mysqlclient
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/InstallMySQLclient.png)

  ```ssh
$ sudo mysql_secure_installation
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/InstallMySQLsecure.png)

## *Start Django Project "Stevens"*

  ```ssh
pi@raspberrypi:~ $ django-admin startproject stevens
pi@raspberrypi:~ $ cd stevens
pi@raspberrypi:~/stevens $ ls
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/StartDjangoProject.png)

  ```ssh
pi@raspberrypi:~/stevens $ python3 manage.py startapp myapp
pi@raspberrypi:~/stevens $ ls
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/StartDjangoApp.png)

  ```ssh
pi@raspberrypi:~ $ sudo mysql -u root -p
Enter password: PASSWORD
MariaDB [(none)]> use mysql
MariaDB [mysql]> select user, host from mysql.user;
MariaDB [mysql]> create user pi@localhost identified by 'PASSWORD';
MariaDB [mysql]> show databases;
MariaDB [mysql]> create database stevens;
MariaDB [mysql]> grant all privileges on stevens.* to pi@localhost;
MariaDB [mysql]> quit
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/MySQLdatabase.png)

  ```ssh
pi@raspberrypi:~/stevens $ cd stevens
pi@raspberrypi:~/stevens/stevens $ ls
asgi.py  __init__.py  __pycache__  settings.py  urls.py  wsgi.py
pi@raspberrypi:~/stevens/stevens $ nano settings.py
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/Settings.png)

  ```ssh
pi@raspberrypi:~/stevens/stevens $ cp ~/iot/lesson4/stevens/urls.py .
pi@raspberrypi:~/stevens/stevens $ cd ..
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/CopyUrls.png)

  ```ssh
pi@raspberrypi:~/stevens $ cd myapp
pi@raspberrypi:~/stevens/myapp $ ls
admin.py  apps.py  __init__.py  migrations  models.py  tests.py  views.py
pi@raspberrypi:~/stevens/myapp $ cp ~/iot/lesson4/stevens/admin.py .
pi@raspberrypi:~/stevens/myapp $ cp ~/iot/lesson4/stevens/models.py .
pi@raspberrypi:~/stevens/myapp $ cp ~/iot/lesson4/stevens/views.py .
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/CopyAdmin.png)

  ```ssh
pi@raspberrypi:~/stevens/myapp $ mkdir static templates
pi@raspberrypi:~/stevens/myapp $ cd templates
pi@raspberrypi:~/stevens/myapp/templates $ mkdir myapp
pi@raspberrypi:~/stevens/myapp/templates $ cd myapp
pi@raspberrypi:~/stevens/myapp/templates/myapp $ cp ~/iot/lesson4/stevens/index.html .
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/CopyIndex.png)

  ```ssh
pi@raspberrypi:~/stevens/myapp/templates/myapp $ nano index.html
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/GoogleMapsAPIkey.png)

  ```ssh
pi@raspberrypi:~/stevens/myapp/templates/myapp $ cd ~/stevens/myapp/static
pi@raspberrypi:~/stevens/myapp/static $ cp ~/iot/lesson4/static/favicon.ico .
pi@raspberrypi:~/stevens/myapp/static $ mkdir myapp
pi@raspberrypi:~/stevens/myapp/static $ cd myapp
pi@raspberrypi:~/stevens/myapp/static/myapp $ cp ~/iot/lesson4/static/*css .
pi@raspberrypi:~/stevens/myapp/static/myapp $ cp ~/iot/lesson4/static/*js .
pi@raspberrypi:~/stevens/myapp/static/myapp $ cd ~/stevens
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/CopyStaticFiles.png)

  ```ssh
pi@raspberrypi:~/stevens $ python3 manage.py makemigrations myapp
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/MakeMigrations.png)

  ```ssh
pi@raspberrypi:~/stevens $ python3 manage.py migrate
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/Migrate.png)

  ```ssh
pi@raspberrypi:~/stevens $ python3 manage.py createsuperuser
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/CreateSuperuser.png)

  ```ssh
pi@raspberrypi:~/stevens $ python3 manage.py runserver
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/RunServer/RunServer1.png)
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/RunServer/RunServer2.png)
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/RunServer/RunServer3.png)
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/RunServer/RunServer4.png)

  ```ssh
View app at http://127.0.0.1:8000

or

pi@raspberrypi:~/stevens $ python3 manage.py runserver 0.0.0.0:8000
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/ServerTerminal.png)
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab4/Images/Django/ViewApp.png)

## *Start Django REST Project "mycpu"*
