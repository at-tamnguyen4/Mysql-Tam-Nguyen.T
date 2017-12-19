### 1.Create database and tables

1. create database
```mysql
create database blog_news;
```
2. create table
```mysql
create table user (
	id int(11) NOT NULL AUTO_INCREMENT,
	full_name varchar(255) NOT NULL,
	email varchar(255)  NOT NULL,
	rank int(4) NOT NULL,
	is_active tinyint(1),
	created_at timestamp NULL,
	PRIMARY KEY (id)
  );

create table category (
  id int(11) NOT NULL auto_increment,
  title varchar(255) NOT NULL,
  description varchar(255),
  primary key (id)
  );

create table news (
 	id int(11) NOT NULL auto_increment,
 	category_id int(11) NOT NULL,
 	title varchar(255) NOT NULL,
 	view int(11) NOT NULL,
 	is_active tinyint(1),
 	content text,
 	created_at timestamp NULL,
 	updated_at timestamp NULL,
 	primary key (id),
 	foreign key (category_id) references category(id)
 );

 create table comment (
 	id int(11) Not Null auto_increment,
 	target_table varchar(20)  NOT NULL,
 	target_id int(11) NOT NULL,
 	user_id int(11) NOT NULL,
 	comment text NOT NULL,
 	created_at timestamp NULL,
 	updated_at timestamp NULL,
 	primary key (id),
 	foreign key (user_id) references user (id)
 );

 create table follow (
 	id int(11) NOT NULL auto_increment,
 	from_user_id int(11) not null,
 	to_user_id int(11) not null,
 	created_at timestamp NULL,
 	primary key (id),
 	foreign key (from_user_id) references user (id),
	foreign key (to_user_id) references user (id)
 );

create table blog (
  id int(11) not null auto_increment,
  category_id int(11) not null,
  user_id int(11) not null,
  title varchar(255) not null,
  view int(11) not null,
  is_active tinyint(1),
  content text,
  created_at timestamp NULL,
  updated_at timestamp NULL,
  primary key (id),
  foreign key (category_id) references category (id),
  foreign key (user_id) references user (id)
);
```