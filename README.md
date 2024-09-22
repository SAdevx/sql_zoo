# sql_zoo
My solutions to [sql zoo tutorials.](https://sqlzoo.net/wiki/SQL_Tutorial)

## Sections
0. [SELECT basics](#select-basics)
1. [SELECT names](#select-names)


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


