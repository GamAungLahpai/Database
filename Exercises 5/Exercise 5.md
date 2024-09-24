# Week 4

## Exercise 5: subqueries

### 1
SELECT country.name
FROM country
WHERE country.iso_country = (
    SELECT airport.iso_country
    FROM airport
    WHERE airport.name LIKE 'Satsuma%'
);
![screenshot](No1.jpg)

### 2
SELECT airport.name
FROM airport
JOIN country ON airport.iso_country = country.iso_country
WHERE country.name = 'Monaco';
![screenshot](No2.jpg)

### 3
SELECT game.screen_name
FROM game
JOIN goal_reached ON game.id = goal_reached.game_id
JOIN goal ON goal_reached.goal_id = goal.id
WHERE goal.name = 'CLOUDS';
![screenshot](No3.jpg)

### 4
SELECT country.name
FROM country
WHERE country.iso_country NOT IN (
    SELECT airport.iso_country
    FROM airport
);
![screenshot](No4.jpg)

### 5
SELECT goal.name
FROM goal
WHERE goal.target = 'WEATHER'
AND goal.name NOT IN (
    SELECT goal.name
    FROM goal
    JOIN goal_reached ON goal.id = goal_reached.goal_id
    JOIN game ON goal_reached.game_id = game.id
    WHERE game.screen_name = 'Heini'
);
![screenshot](No5.jpg)