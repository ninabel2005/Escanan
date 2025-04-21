## Final Lab Task 1 - Events Management DB ##

## Step 1: Create Database ##


Using MySQL workbench, we first create a database umder the name events_db. After that create a events_tbl : this table consist the events_id as the PRIMARY Key and event_name.


CREATE DATABASE   events_DB;

USE events_DB;

CREATE TABLE events_tbl (

event_id INT (10) AUTO_INCREMENT PRIMARY KEY UNIQUE,

event_name VARCHAR (255) NOT NULL
);

DESCRIBE events_tbl;

## Step 2: Create attendees_tbl ##

This table will hold the attendees_id as the PRIMARY Key and also the attendees_name.

CREATE TABLE attendees_tbl (

attendee_id INT (10) AUTO_INCREMENT PRIMARY KEY UNIQUE,

attendee_name VARCHAR (255) NOT NULL

);

DESCRIBE attendees_tbl;


## Step 3: Create events_attendees_tbl ##

This table will links the events_tbl and attendees_tbl using a many-to-many relationship. 
It uses event_id and attendees_id as FOREIGN Keys.
CREATE TABLE events_attendees_tbl (

event_id INT (10),

attendee_id INT (10),

PRIMARY KEY (event_id,attendee_id),

FOREIGN KEY (event_id) REFERENCES events_tbl (event_id)

ON UPDATE CASCADE

ON DELETE RESTRICT,

FOREIGN KEY (attendee_id) REFERENCES attendees_tbl (attendee_id)

ON UPDATE CASCADE

ON DELETE RESTRICT
);

DROP TABLE events_attendees_tbl;

It uses event_id and attendees_id as FOREIGN Keys.

## Step 4: Create events_sponsors_tbl ##

This links sponsors to events with events_id and and sponsor_name.


CREATE TABLE event_sponsors_tbl (

sponsor_id INT (10) AUTO_INCREMENT PRIMARY KEY UNIQUE,

event_id INT (10),

FOREIGN KEY (event_id) REFERENCES events_tbl (event_id)

ON UPDATE CASCADE

ON DELETE RESTRICT,

sponsor_name VARCHAR (255) NOT NULL

);

## Here's the Screenshot for the EDR (See Screenshot) ##

<img src="https://github.com/ninabel2005/Escanan/blob/main/Final%20Lab%20Task%201/images2/ERD.jpg" align="center" height="350" width="600"/>
