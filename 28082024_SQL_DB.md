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


INSERT INTO COMPANY (NAME,AGE,ADDRESS,SALARY)
VALUES ( 'Paul', 32, 'California', 20000.00 );

INSERT INTO COMPANY (NAME,AGE,ADDRESS,SALARY)
VALUES ('Allen', 25, 'Texas', 15000.00 );

INSERT INTO COMPANY (NAME,AGE,ADDRESS,SALARY)
VALUES ('Teddy', 23, 'Norway', 20000.00 );

UPDATE countries SET country_population = 67.97 WHERE country_id = 1;
UPDATE countries SET country_population = 1.87 WHERE country_id = 5;

SELECT * FROM countries;

DELETE FROM people WHERE person_id = 3;

SELECT * FROM people;

```
