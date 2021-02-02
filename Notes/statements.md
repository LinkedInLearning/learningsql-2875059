# SQL Statements

This document provides a list of SQL statements used in the course _Learning SQL Programming_ from LinkedIn Learning.

Note that this list contains statements which are improper (they have syntax errors) and statements which are incorrect (they do not achieve the desired goal).

## 00_02

```SQL
SELECT * FROM people;
```

```SQL
SELECT first_name FROM people;
```

## 01_01

```SQL
SELECT 'Hello, World!;
```

```SQL
SELECT first_name FROM people;
```

```SQL
SELECT last_name FROM people;
```

```SQL
SELECT first_name, last_name FROM people;
```

```SQL
SELECT last_name, first_name FROM people;
```

```SQL
SELECT * FROM people;
```

```SQL
SELECT first_name, state_code, company FROM people;
```

```SQL
SELECT company, first_name, quiz_points FROM people;
```

## 01_02

```SQL
SELECT * FROM people WHERE state_code='CA';
```

```SQL
SELECT * FROM people WHERE state_code='ca';
```

```SQL
SELECT * FROM people WHERE state_code='FL';
```

```SQL
SELECT * FROM people WHERE state_code='WA';
```

```SQL
SELECT * FROM people WHERE state_code='NY';
```

```SQL
SELECT * FROM people WHERE shirt_or_hat='shirt';
```

```SQL
SELECT first_name, last_name FROM people WHERE shirt_or_hat='shirt';
```

```SQL
SELECT first_name, last, name, shirt_or_hat
FROM people
WHERE
shirt_or_hat='shirt';
```

```SQL
/* Improper Statement */
WHERE shirt_or_hat='shirt'
FROM people
SELECT first_name, last_name, shirt_or_hat;
```

```SQL
/* Improper Statement */
FROM people
SELECT first_name, last_name, shirt_or_hat
WHERE shirt_or_hat='shirt';
```

## 01_03

```SQL
SELECT first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt' AND team='Angry Ants';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt' AND team!='Angry Ants';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt' AND team IS 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt' AND team IS NOT 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt' AND team <> 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' OR state_code='CO' AND shirt_or_hat='shirt' AND team IS 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name, shirt_or_hat, state_code FROM people WHERE state_code='CA' OR state_code='CO' AND shirt_or_hat='shirt' AND team IS 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name, shirt_or_hat, state_code FROM people WHERE (state_code='CA' OR state_code='CO') AND shirt_or_hat='shirt' AND team IS 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name, shirt_or_hat, state_code FROM people WHERE state_code='CA' OR (state_code='CO' AND shirt_or_hat='shirt') AND team IS 'Angry Ants';
```

## 01_04

```SQL
SELECT * FROM people WHERE state_code='CA' OR state_code='CO' OR state_code='CT';
```

```SQL
SELECT first_name, last_name, state_Code FROM people WHERE state_code LIKE 'C%';
```

```SQL
SELECT first_name, last_name, state_Code FROM people WHERE first_name LIKE 'A%';
```

```SQL
SELECT first_name, last_name, state_Code FROM people WHERE first_name LIKE 'J%';
```

```SQL
SELECT first_name, last_name, state_Code FROM people WHERE first_name LIKE '%J%';
```

```SQL
SELECT first_name, last_name, state_Code FROM people WHERE first_name LIKE 'b%n';
```

```SQL
SELECT * FROM people WHERE company LIKE '%LLC';
```

```SQL
SELECT * FROM people WHERE company LIKE '%LLC' LIMIT 5;
```

```SQL
SELECT * FROM people WHERE company LIKE '%LLC' LIMIT 10;
```

```SQL
SELECT * FROM people WHERE company LIKE '%LLC' LIMIT 10 OFFSET 5;
```

## 01_05

```SQL
SELECT first_name, last_name FROM people;
```

```SQL
SELECT first_name, last_name FROM people ORDER BY first_name;
```

```SQL
SELECT first_name, last_name FROM people ORDER BY first_name ASC;
```

```SQL
SELECT first_name, last_name FROM people ORDER BY first_name DESC;
```

```SQL
SELECT state_code, last_name, first_name FROM people ORDER BY state_code, last_name;
```

```SQL
SELECT state_code, last_name, first_name FROM people ORDER BY state_code, last_name DESC;
```

## 01_06

```SQL
SELECT first_name FROM people;
```

```SQL
SELECT first_name, LENGTH(first_name) FROM people;
```

```SQL
SELECT DISTINCT(first_name) FROM people;
```

```SQL
SELECT DISTINCT(first_name) FROM people ORDER BY first_name;
```

```SQL
SELECT DISTINCT(shirt_or_hat) FROM people;
```

```SQL
SELECT COUNT(*) FROM people WHERE state_code='CA';
```

```SQL
SELECT COUNT(first_name) FROM people WHERE state_code='CA';
```

```SQL
SELECT COUNT(last_name) FROM people WHERE state_code='CA';
```

## 01_08
```SQL
SELECT first_name, last_name, quiz_points, shirt_or_hat, team
FROM people 
ORDER BY shirt_or_hat, team;
```

## 02_01

```SQL
SELECT first_name, state_code FROM people;
```

```SQL
SELECT first_name, state_code 
FROM people 
JOIN states ON people.state_code=states.state_abbrev;
```

```SQL
SELECT people.first_name, people.state_code, states.division 
FROM people 
JOIN states ON people.state_code = states.state_abbrev;
```

```SQL
SELECT * FROM people JOIN states ON people.state_code=states.state_abbrev;
```

```SQL
SELECT * FROM people 
JOIN states ON people.state_code = states.state_abbrev 
WHERE people.first_name LIKE 'j%' AND states.region = 'South';
```

```SQL
SELECT people.first_name, states.state_name 
FROM people, states 
WHERE people.state_code=states.state_abbrev;
```

```SQL
SELECT ppl.first_name, st.state_name 
FROM people ppl, states st 
WHERE ppl.state_code=st.state_abbrev;
```

## 02_02

```SQL
SELECT people.first_name, people.last_name, people.state_code, states.state_name 
FROM people 
JOIN states 
ON people.state_code=states.state_abbrev;
```

```SQL
SELECT people.first_name, people.last_name, people.state_code, states.state_name 
FROM states 
JOIN people 
ON people.state_code=states.state_abbrev;
```

```SQL
SELECT people.first_name, people.last_name, people.state_code, states.state_name 
FROM states 
LEFT JOIN people 
ON people.state_code=states.state_abbrev;
```

```SQL
SELECT DISTINCT(people.state_code), states.state_name 
FROM states 
LEFT JOIN people 
ON people.state_code=states.state_abbrev;
```

## 02_03

```SQL
/* Incorrect statement */
SELECT first_name, COUNT(first_name) FROM people;
```

```SQL
SELECT first_name, COUNT(first_name) 
FROM people 
GROUP BY first_name;
```

```SQL
/* Incorrect statement */
SELECT first_name, COUNT(first_name) 
FROM people 
GROUP BY last_name;
```

```SQL
SELECT last_name, COUNT(last_name) 
FROM people 
GROUP BY last_name;
```

```SQL
SELECT state_code, COUNT(state_code) 
FROM people 
GROUP BY state_code;
```

```SQL
/* Incorrect Statement */
SELECT state_code, quiz_points, COUNT(quiz_points)
FROM people
GROUP BY quiz_points
```

```SQL
SELECT state_code, quiz_points, COUNT(quiz_points)
FROM people
GROUP BY state_code, quiz_points
```

## 02_05

```SQL
SELECT states.state_name, COUNT(people.shirt_or_hat) 
FROM states 
JOIN people ON states.state_abbrev=people.state_code 
WHERE people.shirt_or_hat='hat'
GROUP BY people.shirt_or_hat, states.state_name;
```

```SQL
SELECT states.division, people.team, count(people.team) 
FROM states
JOIN people ON states.state_abbrev=people.state_code 
GROUP BY states.division, people.team;
```

## 03_02

```SQL
SELECT 4+2;
```

```SQL
SELECT 1/3;
```

```SQL
SELECT first_name, quiz_points FROM people WHERE quiz_points > 70;
```

```SQL
SELECT first_name, quiz_points FROM people WHERE quiz_points >= 70;
```

```SQL
SELECT first_name, quiz_points FROM people WHERE quiz_points >= 70 ORDER BY quiz_points;
```

```SQL
SELECT first_name, quiz_points FROM people WHERE quiz_points <= 70 ORDER BY quiz_points;
```

```SQL
SELECT MAX(quiz_points), MIN(quiz_points) FROM people;
```

```SQL
SELECT SUM(quiz_points) FROM people;
```

```SQL
SELECT team, COUNT(*), SUM(quiz_points), SUM(quiz_points)/COUNT(*) FROM people GROUP BY team;
```

```SQL
SELECT team, COUNT(*), SUM(quiz_points), AVG(quiz_points) FROM people GROUP BY team;
```

## 03_03

```SQL
/* Improper statement */
SELECT first_name, last_name, quiz_points FROM people WHERE quiz_points=MAX(quiz_points);
```

```SQL
SELECT first_name, last_name, quiz_points FROM people WHERE quiz_points=(SELECT MAX(quiz_points) FROM people);
```

```SQL
SELECT * FROM people WHERE state_code=(SELECT state_abbrev FROM states WHERE state_name='Minnesota');
```

## 03_04

```SQL
SELECT first_name, last_name FROM people;
```

```SQL
SELECT LOWER(first_name), UPPER(last_name) FROM people;
```

```SQL
SELECT LOWER(first_name), SUBSTR(last_name, 1, 5) FROM people;
```

```SQL
SELECT REPLACE(first_name, 'a', '-') FROM people;
```

```SQL
SELECT quiz_points FROM people ORDER BY quiz_points;
```

```SQL
SELECT quiz_points FROM people ORDER BY CAST(quiz_points AS CHAR);
```

```SQL
SELECT MAX(CAST(quiz_points AS CHAR)) FROM people;
```

```SQL
SELECT MAX(CAST(quiz_points AS INT)) FROM people;
```

## 03_05

```SQL
SELECT first_name, last_name FROM people;
```

```SQL
SELECT first_name, UPPER(last_name) FROM people;
```

```SQL
SELECT first_name as firstname, UPPER(last_name) as surname FROM people;
```

```SQL
SELECT first_name as firstname, UPPER(last_name) as surname FROM people WHERE firstname='Laura';
```

## 03_07

```SQL
SELECT state_code, max(quiz_points) AS maxpoints, avg(quiz_points) AS avgpts 
FROM people 
GROUP BY state_code 
ORDER BY avgpts DESC;
```

## 04_01

```SQL
INSERT INTO people (first_name) VALUES ('Bob');
```

```SQL
SELECT * FROM people;
```

```SQL
INSERT INTO people 
(first_name, last_name, state_code, city, shirt_or_hat)
VALUES 
('Mary', 'Hamilton', 'OR', 'Portland', 'hat');
```

```SQL
SELECT * FROM people;
```

```SQL
/* Improper Statement */
INSERT INTO people 
(first_name, last_name) 
VALUES 
('George', 'White'), 
('Jenn', 'Smith'), 
('Carol');
```

```SQL
INSERT INTO people 
(first_name, last_name) 
VALUES 
('George', 'White'), 
('Jenn', 'Smith'), 
('Carol', NULL);
```

```SQL
SELECT * FROM people;
```

## 04_02

```SQL
/* Incorrect Statement */
UPDATE people SET last_name = 'Morrison' WHERE first_name='Carlos';
```

```SQL
SELECT last_name FROM people WHERE first_name='Carlos';
```

```SQL
UPDATE people SET last_name = 'Morrison' WHERE last_name='Morrrison';
```

```SQL
SELECT last_name FROM people WHERE first_name='Carlos' AND city='Houston';
```

```SQL
UPDATE people SET last_name='Morrison'  WHERE first_name='Carlos' AND city='Houston';
```

```SQL
SELECT * FROM people WHERE id_number=175;
```

```SQL
UPDATE people SET last_name='Morrison' WHERE id_number=175;
```

```SQL
SELECT * FROM people;
```

```SQL
SELECT * FROM people WHERE company='Fisher LLC';
```

```SQL
UPDATE people SET company='Megacorp Inc' WHERE company='Fisher LLC';
```

```SQL
SELECT * FROM people WHERE company='Fisher LLC';
```

```SQL
SELECT * FROM people WHERE company='Megacorp Inc';
```

## 04_03

```SQL
/* Incorrect Statement */
DELETE FROM people;
```

```SQL
SELECT * FROM people;
```

```SQL
SELECT * FROM people WHERE id_number=1001;
```

```SQL
DELETE FROM people WHERE id_number=1001;
```

```SQL
SELECT * FROM people;
```

```SQL
SELECT * FROM people WHERE quiz_points IS NULL;
```

```SQL
DELETE FROM people WHERE quiz_points IS NULL;
```

```SQL
SELECT * FROM people;
```

```SQL
INSERT INTO people (first_name, last_name, city, state_code, shirt_or_hat, quiz_points, team, signup, age)
VALUES
("Walter", "St. John", "Buffalo", "NY", "hat", "93", "Baffled Badgers", "2021-01-29", NULL),
("Emerald", "Chou", "Topeka", "KS", "shirt", "92", "Angry Ants", "2021-01-29", 34);
```

```SQL
SELECT * FROM people;
```

```SQL
UPDATE people SET shirt_or_hat='shirt' WHERE first_name='Bonnie' AND last_name='Brooks';
```

```SQL
SELECT * FROM people WHERE first_name='Bonnie' AND last_name='Brooks';
```

```SQL
UPDATE people SET shirt_or_hat='shirt' WHERE first_name='Bonnie' AND last_name='Brooks';
```

```SQL
SELECT * FROM people WHERE first_name='Bonnie' AND last_name='Brooks';
```

```SQL
SELECT * FROM people WHERE first_name='Lois' AND last_name='Hart';
```

```SQL
DELETE FROM people WHERE first_name='Lois' AND last_name='Hart';
```

```SQL
SELECT * FROM people WHERE first_name='Lois';
```