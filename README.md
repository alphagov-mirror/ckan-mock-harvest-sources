## Fake CKAN harvest source

Use this repo to create your own WAF harvest source.

### Setup

Create your [virtual environment](https://virtualenvwrapper.readthedocs.io/en/latest/)

`mkvirtualenv fake-ckan_harvest_source`

Install dependencies

`pip install -r requirements.txt`

### Running the fake harvest source server

`python main.py`

### Testing the server

WAF page will default the url index to 0 but otherwise will be dependant on the number provided in the url

Navigate to `http://localhost:8001/1` to see WAF index 1, `http://localhost:8001/2` to see WAF index 2, etc

The url index generates a uniquely repeatable guid so that the harvest source will be harvested.

### Targeting the harvest source from a [docker-ckan](https://github.com/alphagov/docker-ckan) stack

In order to target the fake harvest source use this URL - http://docker.for.mac.localhost:8001/<index number 0 - 99>
