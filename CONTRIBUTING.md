# Installation of Software

The software is tested on ubuntu-14.04. While it can be installed on windows, the same has not been tested.
This page assumes you've downloaded the project git repository. If not please download it before proceeding through installation process.
Feel free to skip any of the installation steps if you already have them installed. 

## INSTALL PYTHON 2.7

Download official python version 2.7.x from here : https://www.python.org/downloads/

Check if pip is installed by typing command -v pip. Run the following command if not installed.
Run Command :	`sudo apt-get install python-pip python-dev build-essential `
		`sudo pip install --upgrade pip `
(Installs Pip) 

Run Command : 	`sudo pip install --upgrade virtualenv`
(Installs virtualenv)


## INSTALL SCAPY


Run Commands :	
    		```
     		cd /tmp
		wget scapy.net
		unzip scapy-latest.zip
		cd scapy-2.*
		sudo python setup.py install
		```
    
(Downloads and installs scapy)

If you have any issues ,check out the official scapy site here : http://www.secdev.org/projects/scapy/doc/installation.html
 

## INSTALL DJANGO 


Run command : `pip install Django `
(Installs Django)



## INSTALL MYSQL

 
Run Command :
    `sudo apt-get install mysql-server`
		`sudo apt-get install mysql-client`
(Installs MySQL)

Remember the username and password you give during installation.

Run command : `mysql`
(Opens mysql terminal. If it gives password error, try running command "mysql -u(Yourusername) -p" .Give password if requested.)

Run command : 	
    `CREATE DATABASE toolinterface;
		SHOW TABLES;`

You should see a new database called toolinterface created.

Run command : 	`exit`


## SETUP PROJECT


Navigate to Capture-and-Replay-Tool/toolgui

Update the username and password entries in DATABASES entry inside toolinterface/settings.py file to the mysql credentials

Run command : `source bin/activate`
(switch to the python virtual envirionment)

Run command :  ` sudo python manage.py migrate
               `` sudo python manage.py makemigrations`

Run command :	`sudo netstat -tap | grep mysql`
(Check if MySQL server is running)

Run command : `sudo python manage.py runserver`
(This starts the Django server)

Open a web browser and type in the url: `localhost:8000/home`. The dashboard of the tool should open. 

Check out [documentation.docx](https://github.com/world-of-open-source/Capture-and-Replay/blob/master/documentation.docx) for project details and quick workarounds.
