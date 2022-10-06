# create SCHEMA `bookbiz01`;
SET SQL_SAFE_UPDATES =0;

CREATE TABLE bookbiz01.publishers(
pub_id char(4) NOT NULL,
pub_name varchar(128) NOT NULL,
adress varchar(128),
city varchar(128),
state varchar(128),
primary key(`pub_id`));

SELECT * FROM publishers;

USE `bookbiz01`;
INSERT INTO publishers (`pub_id`,`pub_name`,`adress`,`city`,`state` )
values ('0010', 'Pagramatics', '4 4th Ln', 'Chicago', 'UD'),
('0877','Binnet & Hardley', '2 2ch Ave', 'Boston', 'DC'),
('1389', 'Albogada Infosystem', '3 3rd Dr', 'Berkley', 'CA');

UPDATE bookbiz01.publishers 
set `city` = 'Atlanta', `state` = 'GA';

delete from bookbiz01.publishers
where pub_id = '0010';
