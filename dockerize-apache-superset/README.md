# Apache Superset

Apache Superset is an open-source software cloud-native application for data exploration and data visualization able to handle data at petabyte scale.

https://github.com/apache/superset

Superset provides: An intuitive interface to explore and visualize datasets, and create interactive dashboards. A wide array of beautiful visualizations to showcase your data. Easy, code-free, user flows to drill down and slice and dice the data underlying exposed dashboards.

It's a Data Visualization tool initially designed by Airbnb and later open sourced for the community. Superset is a Data Exploration platform designed to be visual, intuitive and interactive. It allows to slice, dice and visualize data. It's written in python and uses Flask as web framework library.


# Getting Started - Installing Apache Superset

Step 0 - Install a Docker Engine and Docker Compose. The first step is to make sure you're all set with a working Docker environment. 



Step 1 - Clone Superset's Github repository. Superset's code is hosted on Github.

```bash
git clone https://github.com/apache/superset.git
```


Step 2 - Launch Superset via docker-compose up. 

```bash
cd superset
```

```bash
git checkout latest
```

```bash
docker-compose -f docker-compose-non-dev.yml up
```

```bash
docker-compose up
```

Step 3 - Log In to Superset: http://localhost:8088.


```bash
username: admin
password: admin
```


Configuring Superset

To configure your application, you need to create a file `superset_config.py` and add it to your PYTHONPATH. Here are some of the parameters you can set in that file:

```bash

# Superset specific config
ROW_LIMIT = 5000

SUPERSET_WEBSERVER_PORT = 8088

# Flask App Builder configuration
# Your App secret key
SECRET_KEY = '\2\1thisismyscretkey\1\2\e\y\y\h'

# The SQLAlchemy connection string to your database backend
# This connection defines the path to the database that stores your
# superset metadata (slices, connections, tables, dashboards, ...).
# Note that the connection information to connect to the datasources
# you want to explore are managed directly in the web UI
SQLALCHEMY_DATABASE_URI = 'sqlite:////path/to/superset.db'

# Flask-WTF flag for CSRF
WTF_CSRF_ENABLED = True
# Add endpoints that need to be exempt from CSRF protection
WTF_CSRF_EXEMPT_LIST = []
# A CSRF token that expires in 1 year
WTF_CSRF_TIME_LIMIT = 60 * 60 * 24 * 365

# Set this API key to enable Mapbox visualizations
MAPBOX_API_KEY = ''

```