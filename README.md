# Flask by Example

## Blog Posts

This is the the repo for the Real Python blog series, Flask by Example -

1. [Part One](https://realpython.com/blog/python/flask-by-example-part-1-project-setup/): Setup a local development environment and then deploy both a staging environment and a production environment on Heroku. (current)**
1. [Part Two](http://www.realpython.com/blog/flask-by-example-part-2-postgres-sqlalchemy-and-alembic): Setup a PostgreSQL database along with SQLAlchemy and Alembic to handle migrations.
1. [Part Three](https://realpython.com/blog/python/flask-by-example-part-3-text-processing-with-requests-beautifulsoup-nltk/): Add in the back-end logic to scrape and then process the counting of words from a webpage using the requests, BeautifulSoup, and Natural Language Toolkit (NLTK) libraries.
1. [Part Four](https://realpython.com/blog/python/flask-by-example-implementing-a-redis-task-queue/): Implement a Redis task queue to handle the text processing.
1. [Part Five](https://realpython.com/blog/python/flask-by-example-integrating-flask-and-angularjs/): Setup Angular on the front-end to continuously poll the back-end to see if the request is done.
1. [Part Six](https://realpython.com/blog/python/updating-the-staging-environment/): Push to the staging server on Heroku - setting up Redis, detailing how to run two processes (web and worker) on a single Dyno.
1. [Part Seven](https://realpython.com/blog/python/flask-by-example-updating-the-ui/): Update the front-end to make it more user-friendly.
1. Part Eight: Add the D3 library into the mix to graph a frequency distribution and histogram.

Check out http://realpython.com

## Quick Start

**First steps**

```sh
# create virtualenvwrapper
$ mkvirtualenv wordcounts`

# install requirements
$ pip install -r requirements.txt
```

**Create Post Activate file**

```sh
# create the file in vim
vi $VIRTUAL_ENV/bin/postactivate
# add the following to the file
cd ~/path/to/your/project
export APP_SETTINGS="config.DevelopmentConfig"
export DATABASE_URL="postgresql://localhost/wordcount_dev"
```

**Setup Migrations**

```sh
$ python manage.py db init
$ python manage.py db migrate
$ python manage.py db upgrade
```

**Run**

```sh
# run redis in new terminal window
$ redis server

# run worker in new terminal window
$ workon wordcounts
$ python worker.py

# run the app
python app.py
```