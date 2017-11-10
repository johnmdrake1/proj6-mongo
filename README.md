


Project: Project 6, MongoDB Memos
Author: John Drake, Michal Young
profile:https://github.com/johnmdrake1
repo:https://github.com/johnmdrake1/proj6-mongo

NOTES ON LATENESS: At the time of my intermediate commit right before the project's three day late period
was to end(8:00PM on Thursday) there were a few glaring issues in addition to the project not being completely finished.
These included:
-Dates sorting properly but the memos being mismatched
-Delete functionality not working

Even though the late period allegedly ended at 8, I have made some changes to add to the project's completeness. These can be seen
from my commit history, but I will list them here for ease of reviewing. I will edit the README to add to this list should I make 
any further improvements.
-Fixed delete functionality
-Fixed sorting, values now display with their correct dates and are more properly aligned
-Added this README(was default before)




Description:
An index page and server with all of the values in a MongoDB database collection(in this case a remote database using Mlab).
This collection will consist of text-string memos and a date associated with each, set by the user when the memo is created.
The user, who must be added as a user of this Mlab database in credentials.ini, can then run the server and see which values
are already present in the current collection. By clicking the relevant buttons on the page, the user can add new memos
or delete old ones. Memos are sorted by the date attached to them when they were created.

Instructions-

For end users:

Assuming credentials.ini has been set up with the user account and the server started, localhost:5000 will take the user to 
the main page. From there, the "Click for memo submission form" box will redirect to a creation page. Choose a date(be wary of
which value is month and which is day, as this varies by system/browser) and enter the desired memo string. The send button will
then add this to the database. After memo creation, client should redirect to the main index page and any changes should be 
reflected here. Clicking the "delete" button below any of the new entries should remove it from the database.

For Developers:
Move credentials.ini into root directory/memos folder. The only fields which will likely need to be changed are
DB_USER : A user name for the application/database.  
DB_USER_PW : The associated password

In terminal:
1. cd to project directory
2. make install (installs necessary dependencies in requirements.txt into virtual environment)
3. make run(not make start) will initialize the server
4. localhost:5000 as above
5. ctrl+c in terminal to quit current server process

Brief summary of how everything works:

index.html is the page initially displayed. It is set up to display all "memos" currently in the mongodb database
collection. It does this through flask communication with flask_main.py. index.html also contains a button that links to create.html(the html
page displayed and used when a memo is being created).

create.html has a date field and text entry box. These are the necessary tools for building a memo entry for the mongodb collection.
Once both fields are satisfied, the data is sent through flask to flask_main.py where it is subsequently processed and 
added to the database.

flask_main.py is responsible for connecting to the mlab database and tying everything together, and does the processing for the html files and their inputs and 
outputs. The file retrieves current data stored in the mlab mongodb database collection and communicates it with index.html to 
display using flask, arrow(responsible for the casual, human readable representation of dates of posting), and other resources.  
flask_main also handles transmission of create.html values to mlab, and memo removal functions should the relevant buttons be clicked. 
The memos are also collected and sorted by date in this file, and some arrow humanize exceptions are handled.

 