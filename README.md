# proj6-mongo
Simple list of dated memos kept in MongoDB database

## What is here

A simple Flask app that displays all the dated memos it finds in a MongoDB database.
There is also a 'scaffolding' program, db_trial.py, for inserting a couple records into the database 
and printing them out.  Get db_trial.py working before you try making
your flask app work.  

## What is not here

In addition to the missing functionality in the application, you will
need a MongoDB database, and you will need credentials (user name and
password) both for an administrative user and a regular user.  The
administrative user may be you, but the regular user is your
application.    Your credentials.ini file should include

- DB : The name of your MongoDB database, which may include multiple collections
- DB_USER : A use name for your application.  
- DB_USER_PW : The password your application gives to access your database
- ADMIN_USER : The administrative user for your MongoDB
installation.  If you install MongoDB on your own computer, you need
this for creating a database.  You don't need it if you use a
cloud-hosted MongoDB service. 
- ADMIN_PW : Password for the administrative user.  You need this if
you use create_db.py to initialize your database.  You don't need it
if you use a cloud-hosted MongoDB service
- DB_HOST : The host computer on which your MongoDB database runs.  This
might be 'localhost' or it might be something like ds884198.mlab.com
- DB_PORT : The network port on which your MongoDB database listens.
  If you run MongoDB on your own computer, the default is 27017.  If
  you run MongoDB on MLab or a similar cloud service, it will be a port
  assigned by your cloud service. 

## Functionality you'll add

The user should be able to add dated memos, either from the same index page or from a separate page. 
Memos should be displayed in date order. 
The user should be able to delete memos. 

## Setting up

Our use of the database is pretty simple, but you should anticipate
that installing MongoDB could take some time.  Since you may not be
able to install the same version of MongoDB on your development
computer and your Pi, it will be especially important to test your
project on the Pi.

Using MongoDB on a cloud service like MLab is much easier than
installing it on your own computer.  I strongly suggest you do that
first.  After your project is working satisfactorily, you may want to
install MongoDB on your own computer and adjust your credentials.ini
file to use it. 

The version of MongoDB available for installing on Raspberry Pi with
apt-get is 2.4.  The version you can find for your development
computer is probably 3.x.  You may even have difficulty finding
documentation for 2.4, as it is considered obsolete.  However,
commands that work for 2.4 still seem to work for 3.x, so you should
write your application and support scripts to use 2.4.   The
difference that may cause you the most headaches is in creating
database user accounts (which are different than the Unix accounts for
users). 

In Python, the pymongo API works with both versions of MongoDB, so
it's only the initial setup where you have to be  
careful to use the right version-specific commands. 


Project: Project 6, MongoDB Memos
Author: John Drake
profile:https://github.com/johnmdrake1
repo:https://github.com/johnmdrake1/proj6-mongo

Description:
An index page with all of the values in a MongoDB database(in this case a remote database using Mlab).u 
The user, who must be added as a user of this Mlab database 