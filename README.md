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

/*
create table titles
(title_id char(6) not null, 
title varchar(80) not null,
type char(12) null, 
pub_id char(4) null, 
price int null, 
advance int null, 
ytd_sales int null, 
contract bit not null, 
notes varchar(200) null,
pubdate datetime null)
*/

/*
insert into bookbiz.titles(`title_id`, `title`, `type`, `pub_id`, `price`, `advance`, `ytd_sales`,`contract`, `notes`, `pubdate`)
value('0001', 'Chainsow Man', 'Manga', '0736', '5000', '25', '2000', '', 'A man who id demon ', '05.12.20017'),
('0002', 'Spice and Wolf' , 'Anime', '0002', '2000', '666', '2500', '', 'Loving merchant and wolfgirl', '12.05.2020');
update bookbiz.titles set price = price*2;
*/
/*
select title, pub_name from bookbiz.titles, bookbiz.publishers where publishers.pub_id = titles.pub_id;
select *from bookbiz.titles
select клиент, id_Клиента from turistmag.клиент, turistmag.снаряжение where снаряжение.idСнаряжение = клиент.id_Клиента;
*/
(5 лаба){
SET SQL_SAFE_UPDATES =0;
CREATE DATABASE IF NOT EXISTS bookbiz;

CREATE TABLE bookbiz.titles(title_id char(6) not null, title varchar(80) not null, type char(12) null, pub_id char(4) null, price int null, advance int null,  ytd_sales int null,  contract bit not null, notes varchar(200) null, pubdate datetime null);

SELECT * FROM bookbiz.titles;

insert into bookbiz.titles(title_id, title, type, pub_id, price, advance, ytd_sales,contract, notes, pubdate) 
value('0001', 'GOF', 'PS4', '0736', '5000', '25', '2000', '', 'RPG ', '05.12.20022'), 
('0002', 'Spice and Wolf' , 'PC', '0002', '2000', '666', '2500', '', 'RP', '12.05.2020'); 
DELETE FROM bookbiz.titles WHERE title_id = 0002; 
update bookbiz.titles set price = price*2; 
select title, pub_name from bookbiz.titles, bookbiz01.publishers where publishers.pub_id = titles.pub_id; 
} 
(6 лаба)
{
select title_id, publishers.*from bookbiz.titles, publishers where bookbiz.titles.pub_id = publishers.pub_id;

select pub_id, pub_name
from publishers;

select pub_name, pub_id
from publishers;

select title, advance*2 as Double_Advance
from titles;

select title_id, ytd_sales*price
from titles;

select title_id, ytd_sales*(price-advance)
from titles;
}
