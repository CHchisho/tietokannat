# Yhteen tauluun kohdistuvien kyselyiden harjoitukset

### Tehtävä 1
SELECT * FROM goal;

![ruudunkaappaus.png](img/img.png)

### Tehtävä 2
SELECT name, type FROM airport WHERE iso_country = 'FI';

![ruudunkaappaus.png](img/img_1.png)

### Tehtävä 3
SELECT name FROM airport WHERE iso_country = 'FI' ORDER BY name ASC;

![ruudunkaappaus.png](img/img_2.png)

### Tehtävä 4
SELECT name, type FROM airport WHERE iso_country = 'FI' ORDER BY type ASC, name ASC;

![ruudunkaappaus.png](img/img_3.png)

### Tehtävä 5
SELECT name FROM country WHERE name LIKE 'F%';

![ruudunkaappaus.png](img/img_4.png)

### Tehtävä 6
SELECT name FROM country WHERE name LIKE '%F%';

![ruudunkaappaus.png](img/img_5.png)

### Tehtävä 7
SELECT locationFROM game WHERE screen_name = 'Vesa';

![ruudunkaappaus.png](img/img_6.png)

### Tehtävä 8
SELECT co2_consumed FROM game WHERE screen_name = 'Ilkka';

![ruudunkaappaus.png](img/img_7.png)

### Tehtävä 9
SELECT co2_budget FROM game WHERE screen_name = 'Vesa';

![ruudunkaappaus.png](img/img_8.png)



# Where-osan liitosehto harjoitukset

### Tehtävä 1
SELECT 
    country.name AS "country name",
    airport.name AS "airport name"
FROM 
    country
JOIN 
    airport ON country.iso_country = airport.iso_country
WHERE 
    country.name = 'Iceland';

![ruudunkaappaus.png](img/img_9.png)

### Tehtävä 2
SELECT 
    airport.name AS "airport name"
FROM 
    country
JOIN 
    airport ON country.iso_country = airport.iso_country
WHERE 
    country.name = 'France' AND airport.type = "large_airport";

![ruudunkaappaus.png](img/img_10.png)

### Tehtävä 3
SELECT 
    country.name AS "country_name",
    airport.name AS "airport_name"
FROM 
    country
JOIN 
    airport ON country.iso_country = airport.iso_country
WHERE 
    country.continent = "AN";

![ruudunkaappaus.png](img/img_11.png)

### Tehtävä 4
SELECT 
    airport.elevation_ft 
FROM 
    game
JOIN 
    airport ON game.location = airport.ident
WHERE 
    game.screen_name= 'Heini';

![ruudunkaappaus.png](img/img_12.png)

### Tehtävä 5
SELECT 
    airport.elevation_ft * 0.3048 AS elevation_m
FROM 
    game
JOIN 
    airport ON game.location = airport.ident
WHERE 
    game.screen_name = 'Heini';

![ruudunkaappaus.png](img/img_13.png)


### Tehtävä 6
SELECT 
    airport.name
FROM 
    game
JOIN 
    airport ON game.location = airport.ident
WHERE 
    game.screen_name = 'Ilkka';

![ruudunkaappaus.png](img/img_14.png)

### Tehtävä 7
SELECT 
    country.name
FROM 
    game
JOIN 
    airport ON game.location = airport.ident
JOIN
    country ON country.iso_country = airport.iso_country
WHERE 
    game.screen_name = 'Ilkka';

![ruudunkaappaus.png](img/img_15.png)

### Tehtävä 8
SELECT 
    goal.name
FROM 
    game
JOIN
    goal_reached ON goal_reached.game_id = game.id
JOIN
    goal ON goal.id = goal_reached.goal_id
WHERE 
    game.screen_name = 'Heini';

![ruudunkaappaus.png](img/img_16.png)

### Tehtävä 9
SELECT 
    airport.name
FROM 
    game
JOIN 
    airport ON game.location = airport.ident
JOIN
    country ON country.iso_country = airport.iso_country
WHERE 
    game.screen_name = 'Ilkka';

![ruudunkaappaus.png](img/img_17.png)

### Tehtävä 10
SELECT 
    country.name
FROM 
    game
JOIN 
    airport ON game.location = airport.ident
JOIN
    country ON country.iso_country = airport.iso_country
WHERE 
    game.screen_name = 'Ilkka';

![ruudunkaappaus.png](img/img_18.png)


# Join harjoitukset

### Tehtävä 1
SELECT 
    country.name AS "country name",
    airport.name AS "airport name"
FROM 
    country
JOIN 
    airport ON country.iso_country = airport.iso_country
WHERE 
    country.name = 'Finland' AND airport.scheduled_service = "yes";

![ruudunkaappaus.png](img/img_19.png)

### Tehtävä 2
SELECT 
    game.screen_name,
    airport.name
FROM 
    game
JOIN 
    airport ON game.location = airport.ident;

![ruudunkaappaus.png](img/img_20.png)

### Tehtävä 3
SELECT 
    game.screen_name,
    country.name
FROM 
    game
JOIN 
    airport ON game.location = airport.ident
JOIN
    country ON country.iso_country = airport.iso_country;

![ruudunkaappaus.png](img/img_21.png)

### Tehtävä 4
SELECT 
    airport.name,
    game.screen_name
FROM 
    airport
LEFT JOIN 
    game ON airport.ident = game.location
WHERE 
    airport.name LIKE '%Hels%';

![ruudunkaappaus.png](img/img_22.png)

### Tehtävä 5
SELECT 
    goal.name,
    game.screen_name
FROM 
    goal
LEFT JOIN 
    goal_reached ON goal.id = goal_reached.goal_id
LEFT JOIN 
    game ON game.id = goal_reached.game_id;

![ruudunkaappaus.png](img/img_23.png)




# Sisäkysely harjoitukset

### Tehtävä 1
SELECT 
    country.name
FROM 
    airport
JOIN
    country ON country.iso_country = airport.iso_country
WHERE 
    airport.name LIKE 'Satsuma%';

![ruudunkaappaus.png](img/img_24.png)

### Tehtävä 2
SELECT 
    airport.name
FROM 
    airport
JOIN
    country ON country.iso_country = airport.iso_country
WHERE 
    country.name = "Monaco";

![ruudunkaappaus.png](img/img_25.png)


### Tehtävä 3
SELECT 
    game.screen_name
FROM 
    game
JOIN
    goal_reached ON goal_reached.game_id = game.id
JOIN
    goal ON goal.id = goal_reached.goal_id
WHERE 
    goal.name = 'CLOUDS';

![ruudunkaappaus.png](img/img_26.png)

### Tehtävä 4
SELECT 
    country.name
FROM 
    country
LEFT JOIN 
    airport ON country.iso_country = airport.iso_country
WHERE 
    airport.iso_country IS NULL;

![ruudunkaappaus.png](img/img_27.png)


### Tehtävä 5
SELECT 
    goal.name
FROM 
    goal
WHERE 
    goal.id NOT IN (
        SELECT 
            goal.id
        FROM 
            goal
        LEFT JOIN 
            goal_reached ON goal.id = goal_reached.goal_id
        LEFT JOIN 
            game ON goal_reached.game_id = game.id
        WHERE 
            game.screen_name = 'Heini'
    );

![ruudunkaappaus.png](img/img_28.png)





# Koostetieto kyselyt harjoitukset

### Tehtävä 1
SELECT 
    MAX(airport.elevation_ft) AS "max(elevation_ft)"
FROM 
    airport;

![ruudunkaappaus.png](img/img_29.png)

### Tehtävä 2
SELECT 
    country.continent AS continent,
    COUNT(country.iso_country) AS "count(*)"
FROM 
    country
GROUP BY 
    country.continent;

![ruudunkaappaus.png](img/img_30.png)

### Tehtävä 3
SELECT 
    game.screen_name,
    COUNT(goal_reached.goal_id) AS "count(*)"
FROM 
    goal_reached
LEFT JOIN 
    game ON goal_reached.game_id = game.id
GROUP BY 
    game.screen_name;

![ruudunkaappaus.png](img/img_31.png)


### Tehtävä 4
SELECT 
    game.screen_name
FROM 
    game
WHERE 
    game.co2_budget = (SELECT MIN(game.co2_budget) FROM game)
LIMIT 1;

![ruudunkaappaus.png](img/img_32.png)


### Tehtävä 5
SELECT 
    country.name,
    COUNT(airport.ident) AS "count(*)"
FROM 
    country
LEFT JOIN 
    airport ON country.iso_country = airport.iso_country
GROUP BY 
    country.name
ORDER BY 
    COUNT(airport.ident) DESC,
    country.name ASC
LIMIT 50;

![ruudunkaappaus.png](img/img_33.png)

### Tehtävä 6
SELECT 
    country.name
FROM 
    country
LEFT JOIN 
    airport ON country.iso_country = airport.iso_country
GROUP BY 
    country.iso_country, country.name
HAVING 
    COUNT(airport.ident) > 1000;

![ruudunkaappaus.png](img/img_34.png)


### Tehtävä 7
SELECT 
    name
FROM 
    airport
WHERE 
    elevation_ft = (SELECT MAX(elevation_ft) FROM airport);

![ruudunkaappaus.png](img/img_35.png)


### Tehtävä 8
SELECT 
    country.name 
FROM 
    country
LEFT JOIN 
    airport ON country.iso_country = airport.iso_country
WHERE 
    airport.elevation_ft = (SELECT MAX(elevation_ft) FROM airport);

![ruudunkaappaus.png](img/img_36.png)


### Tehtävä 9
SELECT 
    COUNT(*) AS "count(*)"
FROM 
    goal_reached
LEFT JOIN 
    game ON goal_reached.game_id = game.id
WHERE 
    game.screen_name = 'Vesa';

![ruudunkaappaus.png](img/img_37.png)


### Tehtävä 10
SELECT 
    name
FROM 
    airport
ORDER BY 
    ABS(latitude_deg) DESC
LIMIT 1;

![ruudunkaappaus.png](img/img_38.png)











