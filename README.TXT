Instructions to run the application

Note: We've already done Steps 1 and 2 in class. They're included here for
      completeness

STEP 1: Install the python DB related python modules from the command line:
sudo pip3 install requests flask-mysql flask-wtf flask-sqlalchemy


STEP 2: Set up an account on db4free.net
- Make note of the username/password and database name

STEP 3: Go to the project home directory, and edit the 3 DB variables
    in .flaskenv according to your login credentials on db4free.net:

      FLASK_APP=main.py
      FLASK_DEBUG=1
      DATABASE_NAME='The name of the database you created on db4free.net'
      DATABASE_USERNAME='YOUR username on db4free.net'
      DATABASE_PASSWORD='YOUR password on db4free.net'

STEP 4: Run the flask application just to initialize the environment variables.
	Type the following in the terminal:

	flask run    (this will start the flask application)
	Ctrl+c       (this will terminate the application)

STEP 5: Still from the project directory, perform the following:
    a. Start python interpreter by typing:     python3
    b. At the python prompt type:              from app import app
    c. At the python prompt type:              from app import db
    d. At the python prompt type:              db.create_all()
    e. Exit the python interpreter by typing:  quit()

The create_all command creates the database schema defined in app/models.py.
Go to db4free.net and click on myPhpAdmin link (this is very slow).  You should
find your table there.

STEP 6: Now run the Flask application from the project home directory:

    flask run --host=0.0.0.0 --port=8080


NOTE: If you make modifications to your DB models in models.py you should
      wipe out and recreate the tables in your database.  This can be done by
      following steps 5.a-c above, and then typing:  db.drop_all()

      You'd then need to call db.create_all() again to recreate the tables.

      Alternatively, the application includes the route /delete_db, which
      accomplishes the same thing (It's an option in the navbar)
