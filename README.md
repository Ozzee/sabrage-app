# Sabrage-App

An application that includes only the sabrage library. You can use
this app if you just want to install a runnable version of Sabrage.

## Development

1. Create a virtualenv for the python packages:  
  * `python3 -m venv virtualenv`
2. Use your new virtualenv:
  * `source virtualenv/bin/activate`
  * You will need to do this every time you start a new terminal session
3. Install dependencies:
  * `pip install -r requirements.txt`
4. Run migrations:
  * `./manage.py migrate`
5. Create a superuser account
  * `./manage.py createsuperuser`
6. Run the server:
  * `./manage.py runserver`
7. Go to the admin UI and create some items
  * http://127.0.0.1:8000/admin/
8. Now you should be ready to test
  * http://127.0.0.1:8000/sabrage/

## Installation

### Heroku

The application is set up to be deployable to Heroku. You just need to push
it to your app there. Note that the databse in this default configuration
is an SQLite file based database which should never ever be used for real
on Heroku (and rarely anywhere else).

`git push heroku master`

### Apache

To deploy the application with Apache mod_wsgi, have a look at the
documentation here: https://docs.djangoproject.com/en/1.10/howto/deployment/wsgi/modwsgi/

You don't even need to care about the static files setup, as this app uses
whitenoise to serve those through Django too.