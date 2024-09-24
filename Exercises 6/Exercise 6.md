# Week 5

## Exercise 6: aggregate queries

### 1
SELECT MAX(elevation_ft)
FROM airport;
![screenshot](No1.jpg)

### 2
SELECT continent, COUNT(*)
FROM country
GROUP BY continent;
![screenshot](No2.jpg)

### 3
SELECT g.screen_name, COUNT(gr.goal_id)
FROM game g
LEFT JOIN goal_reached gr ON g.id = gr.game_id
LEFT JOIN goal go ON gr.goal_id = go.id AND go.target = 'WEATHER'
GROUP BY g.screen_name;
![screenshot](No3.jpg)

### 4
SELECT screen_name
FROM game
WHERE co2_consumed = (
    SELECT MIN(co2_consumed)
    FROM game
);
![screenshot](No4.jpg)

### 5
SELECT country.name, COUNT(*) AS airport_count
FROM country
JOIN airport ON country.iso_country = airport.iso_country
GROUP BY country.name
ORDER BY airport_count DESC
LIMIT 50;
![screenshot](No5.jpg)

### 6
SELECT country.name
FROM country
JOIN airport ON country.iso_country = airport.iso_country
GROUP BY country.name
HAVING COUNT(airport.id) > 1000
ORDER BY COUNT(airport.id) DESC;
![screenshot](No6.jpg)

### 7
SELECT name
FROM airport
WHERE elevation_ft = (SELECT MAX(elevation_ft) FROM airport);
![screenshot](No7.jpg)

### 8
SELECT country.name
FROM airport
JOIN country ON airport.iso_country = country.iso_country
WHERE airport.elevation_ft = (SELECT MAX(elevation_ft) FROM airport);
![screenshot](No8.jpg)

### 9
SELECT COUNT(*)
FROM goal_reached gr
JOIN goal g ON g.id = gr.goal_id
JOIN game ga ON gr.game_id = ga.id
WHERE g.target = 'WEATHER'
AND ga.screen_name = 'Vesa';
![screenshot](No9.jpg)

### 10
SELECT name
FROM airport
WHERE latitude_deg = -90;
![screenshot](No10.jpg)







