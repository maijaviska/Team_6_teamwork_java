```sql
CREATE TABLE people (
	person_id INTEGER PRIMARY KEY,
	name TEXT,
	surname TEXT,
	age INTEGER
);
	
INSERT INTO people VALUES (1, 'Bob', 'Johnson', 32);
INSERT INTO people VALUES (2, 'Anna', 'Liepa', 24);
INSERT INTO people VALUES (3, 'Susanna', 'Stiller', 41);
INSERT INTO people VALUES (4, 'William', 'Anderson', 55);

CREATE TABLE countries (
	country_id INT PRIMARY KEY,
	country_name TEXT,
	capital_city TEXT,
	country_population INT DEFAULT 10000
);
	
INSERT INTO countries VALUES (1, 'France', 'Paris', 3);
INSERT INTO countries VALUES (2, 'Italy', 'Rome', 58.94);
INSERT INTO countries VALUES (3, 'Poland', 'Warsaw', 36.82);
INSERT INTO countries VALUES (4, 'Lithuania', 'Vilnius', 2.83);
INSERT INTO countries (country_id, country_name, capital_city)
VALUES (5, 'Latvia', 'Riga');

CREATE TABLE Company(
   ID INTEGER PRIMARY KEY AUTOINCREMENT,
   NAME           TEXT      NOT NULL,
   AGE            INT,
   ADDRESS        CHAR(50),
   SALARY         REAL
);
```
