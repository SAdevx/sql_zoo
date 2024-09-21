# sql_zoo
My solutions to [sql zoo tutorials.](https://sqlzoo.net/wiki/SQL_Tutorial)

## Sections
0. [SELECT basics](#0-select-basics)

    1. 
            SELECT population FROM world
            WHERE name = 'Germany';
    2. 
            SELECT name, population FROM world 
            WHERE name IN ('Sweden', 'Norway', 'Denmark');
    3.
            SELECT name, area FROM world
            WHERE area BETWEEN 200000 AND 250000;