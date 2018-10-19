Deploying a Basic User Service

You will need to install Python3.6 to host an instance, along with several packages. Installation instructions are below:

### Installation on Ubuntu 14.04

First, install Python and Pip:

`sudo apt-get install python3 python3-pip`

Next, install relevant Python packages:

`sudo pip3 install Django==2.0.7`
Django version 2.0.7 is necessary, since version 2.1 does not work with the default installation of Python3.

`sudo pip3 install gunicorn whitenoise dj-database-url psycopg2-binary django-heroku`

After this succeeds, installation should be complete.

You can then start the server with the command:
`python3 manage.py runserver 0.0.0.0:8000`
This will run the server on port 8000, and allow connections from other machines as long as your IP has been added to `ALLOWED_HOSTS` in `settings.py`.

