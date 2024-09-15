# Week 3

## Exercise 2: single table Queries

### 1
use flight_game;
select * from flight_game.goal
![screenshot](No1.jpg)

### 2
USE flight_game;
SELECT name, type FROM flight_game.airport WHERE iso_country = "FI";
![screenshot](No2.jpg)

### 3
USE flight_game;
SELECT name FROM flight_game.airport WHERE iso_country = "FI"
ORDER BY name ASC;
![screenshot](No3.jpg)

### 4
USE flight_game;
SELECT name, type
FROM flight_game.airport
WHERE iso_country = "FI"
ORDER BY type ASC;
![screenshot](No4.jpg)

### 5
USE flight_game;
SELECT name
FROM flight_game.country
WHERE name LIKE 'F%';
![screenshot](No5.jpg)

### 6
USE flight_game;
SELECT name 
FROM flight_game.country 
WHERE name LIKE '%F%' 
ORDER BY name ASC;
![screenshot](No6.jpg)

### 7
USE flight_game;
SELECT location 
FROM flight_game.game
WHERE game.screen_name = 'Vesa';
![screenshot](No7.jpg)

### 8
USE flight_game;
SELECT co2_consumed
FROM flight_game.game
WHERE game.screen_name = 'Ilkka';
![screenshot](No8.jpg)

### 9
USE flight_game;
SELECT co2_budget
FROM flight_game.game
WHERE game.screen_name = 'Ilkka';
![screenshot](No9.jpg)

### 10
SELECT 'Ilkka' AS screen_name, 10000 AS co2_budget, 8000 AS co2_consumed, 10000 - 8000 AS co2_left;
![screenshot](No10.jpg)

