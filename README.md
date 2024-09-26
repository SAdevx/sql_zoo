# sql_zoo
My solutions to [sql zoo tutorials.](https://sqlzoo.net/wiki/SQL_Tutorial)

## Sections
0. [SELECT basics](#select-basics)
1. [SELECT names](#select-names)
2. [SELECT from world](#select-from-world)


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
working on solution progress
```
14.
```sql
working on solution progress
```
15.
```sql
working on solution progress
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
