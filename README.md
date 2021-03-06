[![Live Demo](https://img.shields.io/badge/live%20demo-active-brightgreen.svg?style=flat-square)](https://ancient-earth-46456.herokuapp.com/)

Tech Quote: Host technology-related quotes
==========================================

About
-----
From Udacity:
> You will develop an application that provides a list of items within a
> variety of categories as well as provide a user registration and
> authentication system. Registered users will have the ability to post,
> edit, and delete their own items.

Supporting courses:

* [Full Stack Foundations](https://www.udacity.com/course/full-stack-foundations--ud088)
* [Authentication & Authorization: OAuth](https://www.udacity.com/course/authentication-authorization-oauth--ud330)

Tech Quote (TQ) hosts technology-related quotes, specifically quotes relating
to programming languages. The TQ application meets all requirements for
the [Item Catalog](https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd004) 
project by implementing the following:

* JSON API endpoint at `quote/api/v1/quotes`
```javascript
// quote/api/v1/quotes payload example
{
	"quotes": [{
		"author": {
			"bio": "http://stackoverflow.com/users/2705542/tim-peters",
			"name": "Tim Peters"
		},
		"category": {
			"description": "Python is a widely used general-purpose, high-level programming language. Its design philosophy emphasizes code readability, and its syntax allows programmers to express concepts in fewer lines of code than would be possible in languages such as C++ or Java. The language provides constructs intended to enable clear programs on both a small and large scale.",
			"name": "Python"
		},
		"created": "Sun, 29 Nov 2015 22:18:01 GMT",
		"quote": "Special cases aren't special enough to break the rules.",
		"source": "https://www.python.org/dev/peps/pep-0020/"
	}, ... ]
}
```
* Data is read from a PostgreSQL database using SQLAlchemy
* Forms exist for adding/editing data with server-side validation and
  CSRF protection with WTForms
* Data created by a user can can be deleted by (only) that user as a POST
  request and with CSRF protection
* OAuth2 login via GitHub
* Code is well organized, and self-documenting via Sphinx
* Code adheres to PEP8 and PEP257
* Images can be uploaded by a user

**Flask Extensions**: Assets, Login, Migrate, Script, SQLAlchemy, Uploads,
    and WTF

**Flask Patterns**: Packages, Blueprints, Application factory,
    View decorators (login & template rendering), Template inheritance,
    Message flashing, and Custom error pages

**CSS/JS Libraries**:  Bootstrap v3, Bootstrap Social, Selectize.js,
    Font-Awesome

Deployment
----------
This project was deployed on Heroku using their free-tier service. This means that the readable app will "go to sleep" after 30 minutes of inactivity. This translates to a very slow first startup as the Heroku dynos that run the application will need to be brought up first.

Requirements
------------

* [Vagrant](http://www.vagrantup.com/downloads.html)

Configuration
-------------

All configuration is accomplished by environmental variables.
The following variables are available:

*APP_SETTINGS* 
- Configuration object to be used to run application.

*DATABASE_URL*
- Database connection string to connect to application database.

*GITHUB_ID*
- OAuth2 client id provided by GitHub for access to API.

*GITHUB_SECRET*
- OAuth2 client secret provided by GitHub for access to API.

*TQ_SECRET*
- A byte string which is the master key by which all form values are encoded.
  Set to a sufficiently long string of characters that is difficult to
  guess or bruteforce (recommended at least 16 characters) for example
  the output of os.urandom(16).

Install
-------

1. `git clone https://github.com/brenj/fullstack-nanodegree-vm.git fullstack && cd fullstack/vagrant`
2. `vagrant up`
3. `vagrant ssh`
4. `cd /vagrant/tech-quote`
5. `virtualenv venv && . venv/bin/activate`
6. `. bin/set-env-vars.sh` (after updating configuration values in `.env`, see Configuration)
7. `make install`
8. `make prod` or `make dev` (depending on the configuration)

Documentation
-------------
API Documentation is generated by Sphinx autodoc.

1. `make doc`

Grading (by Udacity)
--------------------

Criteria       |Highest Grade Possible  |Grade Recieved
---------------|------------------------|--------------
API Endpoints  |Exceeds Specifications  |Meets Specifications
CRUD: Create   |Exceeds Specifications  |Exceeds Specifications
CRUD: Read     |Exceeds Specifications  |Exceeds Specifications
CRUD: Update   |Exceeds Specifications  |Exceeds Specifications
CRUD: Delete   |Exceeds Specifications  |Exceeds Specifications
Authentication & Authorization   |Meets Specifications  |Meets Specifications
Code Quality   |Meets Specifications  |Meets Specifications
Comments       |Meets Specifications  |Meets Specifications
Documentation  |Meets Specifications    |Meets Specifications
