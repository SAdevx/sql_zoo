# sql_zoo

My solutions to [sql zoo tutorials.](https://sqlzoo.net/wiki/SQL_Tutorial)

## Sections

0. [SELECT basics](#select-basics)
1. [SELECT names](#select-names)
2. [SELECT from world](#select-from-world)
3. [SELECT from nobel](#select-from-nobel)
4. [SELECT within SELECT](#select-within-select)
5. [SUM COUNT](#sum-and-count)
6. [JOIN OPERATION](#join-operation)
7. [MORE JOIN OPERATION](#more-join-operation)

## SELECT basics

1.

```sql
SELECT population FROM world
WHERE name = 'Germany';
```

2.

```sql
SELECT name, population FROM world
WHERE name IN ('Sweden', 'Norway', 'Denmark');
```

3.

```sql
SELECT name, area FROM world
WHERE area BETWEEN 200000 AND 250000;
```

## SELECT names

1.

```sql
SELECT name FROM world
WHERE name LIKE 'Y%';
```

2.

```sql
SELECT name FROM world
WHERE name LIKE '%Y';
```

3.

```sql
SELECT name FROM world
WHERE name LIKE '%X%';
```

4.

```sql
SELECT name FROM world
WHERE name LIKE '%land';
```

5.

```sql
SELECT name FROM world
WHERE name LIKE 'C%ia';
```

6.

```sql
SELECT name FROM world
WHERE name LIKE '%oo%';
```

7.

```sql
SELECT name FROM world
WHERE name LIKE '%a%a%a%';
```

8.

```sql
SELECT name FROM world
WHERE name LIKE '_t%';
ORDER BY name
```

9.

```sql
SELECT name FROM world
WHERE name LIKE '%o__o%';
```

10.

```sql
SELECT name FROM world
WHERE name LIKE '____';
```

11.

```sql
SELECT name FROM world
WHERE name = capital;
```

12.

```sql
SELECT name FROM world
WHERE capital = concat(name,' City');
```

13.

```sql
SELECT capital, name FROM world
WHERE capital LIKE concat('%',name,'%');
```

14.

```sql
working on solution
```

15.

```sql
working on solution
```

## SELECT from world

1.

```sql
SELECT name, continent, population FROM world;
```

2.

```sql
SELECT name FROM world
WHERE population >= 200000000;
```

3.

```sql
SELECT name, gdp/population FROM world
WHERE population >= 200000000;
```

4.

```sql
SELECT name, population/1000000 FROM world
WHERE continent = 'South America';
```

5.

```sql
SELECT name, population FROM world
WHERE name IN ('France', 'Germany', 'Italy');
```

6.

```sql
SELECT name FROM world
WHERE name LIKE '%United%';
```

7.

```sql
SELECT name FROM world
WHERE name LIKE '%United%';
```

8.

```sql
SELECT name, population, area FROM world
WHERE area > 3000000 AND population < 250000000
OR area < 3000000 AND population > 250000000;
```

9.

```sql
SELECT name, ROUND(population/1000000,2), ROUND(gdp/1000000000,2) FROM world
WHERE continent IN ('South America');
```

10.

```sql
SELECT name, ROUND(gdp/population,-3) FROM world
WHERE gdp > 1000000000000;
```

11.

```sql
SELECT name, capital FROM world
WHERE LENGTH(name) = LENGTH(capital);
```

12.

```sql
SELECT name, capital FROM world
WHERE name <> capital AND LEFT(name,1) = LEFT(capital,1);
```

13.

```sql
SELECT name FROM world
WHERE name NOT LIKE '% %'
AND name LIKE '%a%'
AND name LIKE '%e%'
AND name LIKE '%i%'
AND name LIKE '%o%'
AND name LIKE '%u%';
```

## SELECT from nobel

1.

```sql
SELECT yr, subject, winner
FROM nobel WHERE yr = 1950;
```

2.

```sql
SELECT winner FROM nobel
WHERE yr = 1962 AND subject = 'literature';
```

3.

```sql
SELECT yr, subject FROM nobel
WHERE winner = 'Albert Einstein';
```

4.

```sql
SELECT winner FROM nobel
WHERE subject = 'peace' AND yr >= 2000;
```

5.

```sql
SELECT * FROM nobel
WHERE subject = 'literature'
AND yr >= 1980 AND yr <= 1989;
```

6.

```sql
SELECT * FROM nobel
WHERE winner IN ('Theodore Roosevelt','Woodrow Wilson','Jimmy Carter','Barack Obama');
```

7.

```sql
SELECT winner FROM nobel
WHERE winner LIKE 'John%';
```

8.

```sql
SELECT * FROM nobel
WHERE subject = 'physics' AND yr = 1980
OR subject = 'chemistry' AND yr = 1984;
```

9.

```sql
SELECT * FROM nobel
WHERE yr = 1980 AND subject NOT IN ('Chemistry','Medicine');
```

10.

```sql
SELECT * FROM nobel
WHERE subject IN ('Medicine') AND yr < 1910
OR subject IN ('Literature') AND yr >= 2004;
```

11.

```sql
SELECT * FROM nobel
WHERE winner = 'PETER GRÜNBERG';
```

12.

```sql
SELECT * FROM nobel
WHERE winner = 'EUGENE O\'NEILL';
```

13.

```sql
SELECT winner, yr, subject FROM nobel
WHERE winner LIKE 'Sir%' ORDER BY yr DESC, winner;
```

14.

```sql
SELECT winner, subject FROM nobel
WHERE yr = 1984
ORDER BY subject IN ('Chemistry','Physics'), subject, winner;
```

## SELECT within SELECT

1.

```sql
SELECT name FROM world
WHERE population > (SELECT population FROM world
WHERE name = 'Russia');
```

2.

```sql
SELECT name FROM world
WHERE continent = 'Europe'
AND (gdp/population) >
(SELECT gdp/population FROM world
WHERE name = 'United Kingdom');
```

3.

```sql
SELECT name, continent FROM world
WHERE continent = (SELECT continent FROM world WHERE name = 'Argentina')
OR continent = (SELECT continent FROM world WHERE name = 'Australia')
ORDER BY name;
```

4.

```sql
SELECT name, population FROM world
WHERE population > (SELECT population FROM world WHERE name = 'United Kingdom')
AND population < (SELECT population FROM world WHERE name = 'Germany');
```

5.

```sql
SELECT name, CONCAT(ROUND((population / (SELECT population
FROM world WHERE name = 'Germany')*100),0),'%') AS percentage FROM world
WHERE continent = 'Europe';
```

6.

```sql
solution in progress
```

7.

```sql
solution in progress
```

8.

```sql
solution in progress
```

9.

```sql
solution in progress
```

10.

```sql
solution in progress
```


## SUM and COUNT

1.

```sql
SELECT SUM(population) FROM world;
```

2.

```sql
SELECT DISTINCT continent
FROM world;
```

3.

```sql
SELECT SUM(gdp) FROM world
WHERE continent = 'Africa';
```

4.

```sql
SELECT COUNT(name) FROM world
WHERE area >= 1000000;
```

5.

```sql
SELECT SUM(population) FROM world
WHERE name IN ('Estonia','Latvia','Lithuania');
```

6.

```sql
SELECT continent,COUNT(name) FROM world
GROUP BY continent;
```

7.

```sql
SELECT continent, COUNT(name) FROM world
WHERE population > 10000000
GROUP BY continent;
```

8.

```sql
SELECT continent FROM world
GROUP BY continent HAVING SUM(population) > 100000000;
```

## JOIN OPERATION

1.

```sql
SELECT matchid, player FROM goal
WHERE teamid = 'GER';
```

2.

```sql
SELECT id,stadium,team1,team2
FROM game WHERE id = 1012;
```

3.

```sql
SELECT player,teamid,stadium,mdate
FROM game JOIN goal ON (id=matchid)
WHERE teamid = 'GER';
```

4.

```sql
SELECT team1, team2, player
FROM game JOIN goal ON (id=matchid)
WHERE player LIKE 'Mario%';
```

5.

```sql
SELECT player, teamid, coach, gtime
FROM goal JOIN eteam ON (teamid=id)
WHERE gtime<=10;
```

6.

```sql
SELECT mdate, teamname FROM game
JOIN eteam ON (team1=eteam.id)
WHERE coach = 'Fernando Santos';
```

7.

```sql
SELECT player FROM goal
JOIN game ON (id=matchid)
WHERE stadium = 'National Stadium, Warsaw';
```

8.

```sql
solution in progress
```

9.

```sql
solution in progress
```

10.

```sql
solution in progress
```

11.

```sql
solution in progress
```

12.

```sql
solution in progress
```

13.

```sql
solution in progress
```

## MORE JOIN OPERATION

1.

```sql
SELECT id, title FROM movie WHERE yr=1962;
```

2.

```sql
SELECT yr FROM movie
WHERE title = 'Citizen Kane';
```

3.

```sql
SELECT id, title, yr FROM movie
WHERE title LIKE '%Star%'
AND title LIKE '%Trek%'
ORDER BY yr;
```

4.

```sql
SELECT actor.id FROM actor
WHERE name='Glenn Close';
```

5.

```sql
SELECT id FROM movie
WHERE title='Casablanca';
```

6.

```sql
SELECT name FROM movie
JOIN casting ON movie.id=casting.movieid
JOIN actor ON actor.id=casting.actorid
WHERE movieid=11768;
```

7.

```sql
SELECT name FROM movie
JOIN casting ON movie.id=casting.movieid
JOIN actor ON actor.id=casting.actorid
WHERE title='Alien';
```

8.
```sql
SELECT title FROM movie
JOIN casting ON movie.id=movieid
JOIN actor ON actorid=actor.id
WHERE name = 'Harrison Ford';
```

9.
```sql
SELECT title FROM movie
JOIN casting ON movie.id=movieid
JOIN actor ON actor.id=actorid
WHERE name='Harrison Ford' AND ord != 1;
```

10.
```sql
SELECT title,name FROM movie
JOIN casting ON movie.id=movieid
JOIN actor ON actor.id = actorid
WHERE yr=1962 && ord=1;
```

11.
```sql
SELECT yr,COUNT(title) FROM
movie JOIN casting ON movie.id=movieid
OIN actor   ON actorid=actor.id
WHERE name='Rock Hudson'
GROUP BY yr
HAVING COUNT(title) > 2
```