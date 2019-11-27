# fir-2019
Datenmodellierung und -analyse mit SQL und Python


# Download SQLite3

https://sqlite.org/2019/sqlite-tools-win32-x86-3300100.zip

# Datenbank für Niederschlag einrichten

```
CREATE TABLE niederschlag (id integer primary key autoincrement, 
                           year integer, 
                           month integer, 
                           day integer, 
                           state_code integer, 
                           state text(3), 
                           station_id text, 
                           zeitslot integer, 
                           menge integer);

```
