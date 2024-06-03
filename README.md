create table genres (id SERIAL primary key , genre varchar(50) not null ); 

create table performers (id SERIAL primary key , name varchar(50) not null);

create table list_of_artists_for_genres (id_genre INTEGER references genres (id), id_performer INTEGER references performers (id));

create table albums (id SERIAL primary key , title varchar(50) not null, year_of_release DATE not null check(year_of_release > 1900));
 
create table albums_and_artists (id_performer INTEGER references performers (id), id_album INTEGER references albums (id)); 

create table tracks (id SERIAL primary key , title varchar(50) not null, duration integer not null check(duration < 1000 ), id_album INTEGER references albums (id));

create table Collections (id SERIAL primary key , title varchar(50) not null, year_of_release DATE not null check(year_of_release > 1900));

create table Collections_and_tracks (Collection_ID INTEGER references Collections (id), Track_ID INTEGER references tracks (id)); 
