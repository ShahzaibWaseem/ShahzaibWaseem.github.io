---
title: School Ranking System
date:   2018-01-09
tags: 
  - Python3
  - JavaScript
  - SQLite
  - Flask
  - Jinja
  - SQL Alchemy
  - Flask's Login Manager
  - WT Forms
  - Werkzeug Security
  - sha256 encryption
  - HTML
  - CSS
  - Bootstrap
toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---

**Languages Used**: Python3, JavaScript, SQLite

**Source Code**: [GitHub Link](https://github.com/ShahzaibWaseem/Project-Database)

## Goal
The goal of this project was to guide students in the country by ranking schools and colleges, based on the maximum and minimum percentage marks got by the school's existing students, in the respected student's city. This would be an all-in-one system which tells the student about the fee for a particular school or college, if the school offers a scholarship to its students, what courses does the school offers and would it be possible for the student to get into the school based on his/her grades.

## Tools & Libraries
- Flask
- Jinja
- SQL Alchemy
- Flask's Login Manager (secure login & signup pages)
- Flask WT Forms and Validators
- Werkzeug Security (sha256 encryption)

## Description
School Ranking System, which has Flask-Python at the back-end and Jinja templates at the front-end, This is a demonstration for "Database Systems".  The Project has three different views for the three different types of users:
- Admin: Can view, add and delete entries. Highest level of control.
- Partial Admin: Can view and add entries to the database, because deletion should be in the hands of the Administrator.
- Regular User: Student; Can only view the tables and the graphs (made on JavaScript).

The views are generated, on *run time* using *Jinja Templating Language*, for the differnt user types, when the user signs in. The views are made using Bootstrap for CSS styling and the bar graphs were made using JavaScript. Special attention was given to the security and robustness of the system; Flask's WTForms and validators were used to make the forms for adding records and the usernames and passwords were saved in the SQLite database, `DB-Project.db`, and the passwords were sha256 encrypted, meaning that the raw passwords were not saved in the database but were encrypted using Werkzeug Security and then saved to the database, so even the Database Administrator can not see what the user has set his/her password.

### UML Diagram
![UML Diagram of "School Ranking System"](https://github.com/ShahzaibWaseem/Project-Database/blob/master/UML.png?raw=true)

## How to run Flask
```console
$ python3 -m venv venv
$ . venv/bin/activate
$ pip3 install Flask
$ export FLASK_APP=application.py
$ flask run
```

## References
Find this amazing article to get Flask up and running, with an Example, [here](https://dev.to/sahilrajput/install-flask-and-create-your-first-web-application-2dba) or visit the [Flask Homepage](https://flask.palletsprojects.com/en/1.1.x/installation/) for more details to learn more about Flask and the other tools used in the project.

You can fork the project on [GitHub](https://github.com/ShahzaibWaseem/Project-Database) to add more features to the project.