+ [1](#1)
+ [2](#2)
+ [3](#3)
+ [4](#4)
+ [5](#5)
+ [6](#6)
+ [7](#7)
+ [8](#8)
+ [9](#9)
+ [10](#10)
+ [11](#11)
+ [12](#12)
+ [13](#13)
+ [14](#14)
+ [15](#15)
+ [16](#16)
+ [17](#17)
+ [18](#18)
+ [19](#19)
+ [20](#20)

## 1

https://sql-ex.ru/learn_exercises.php?LN=1

```sql
SELECT model, speed, hd
FROM PC
WHERE price < 500
```

## 2

https://sql-ex.ru/learn_exercises.php?LN=2

```sql
SELECT DISTINCT maker FROM Product WHERE type='Printer'
```

## 3

https://sql-ex.ru/learn_exercises.php?LN=3

```sql
SELECT model, ram, screen FROM laptop WHERE price > 1000
```

## 4

https://sql-ex.ru/learn_exercises.php?LN=4

```sql
SELECT * FROM Printer WHERE color = 'y' 
```

## 5

https://sql-ex.ru/learn_exercises.php?LN=5

```sql
SELECT model, speed, hd FROM PC WHERE (cd = '12x' OR cd = '24x') AND price < 600
```

## 6

https://sql-ex.ru/learn_exercises.php?LN=6

```sql
SELECT DISTINCT maker, speed 
FROM Laptop 
JOIN Product ON Laptop.model = Product.model
WHERE hd >= 10
```

## 7

https://sql-ex.ru/learn_exercises.php?LN=7

```sql
SELECT DISTINCT Product.model, PC.price
FROM Product JOIN PC ON Product.model = PC.model WHERE maker = 'B'
UNION
SELECT DISTINCT Product.model, Laptop.price
FROM Product JOIN Laptop ON Product.model = Laptop.model WHERE maker = 'B'
UNION
SELECT DISTINCT Product.model, Printer.price
FROM Product JOIN Printer ON Product.model = Printer.model WHERE maker = 'B'
```

## 8

https://sql-ex.ru/learn_exercises.php?LN=8

```sql
SELECT maker FROM Product WHERE type = 'PC'
EXCEPT
SELECT maker FROM Product WHERE type = 'Laptop'
```

## 9

https://sql-ex.ru/learn_exercises.php?LN=9

```sql
SELECT DISTINCT maker
FROM Product
JOIN PC ON Product.model = PC.model
WHERE speed >= 450
```

## 10

https://sql-ex.ru/learn_exercises.php?LN=10

```sql
SELECT model, price FROM Printer WHERE price =
(SELECT MAX(price) FROM Printer )
```

## 11

https://sql-ex.ru/learn_exercises.php?LN=11

```sql
SELECT AVG(speed) FROM PC
```

## 12

https://sql-ex.ru/learn_exercises.php?LN=12

```sql
SELECT AVG(speed) FROM Laptop WHERE price > 1000
```

## 13

https://sql-ex.ru/learn_exercises.php?LN=13

```sql
SELECT AVG(speed)
FROM PC
JOIN Product ON PC.model = Product.model
WHERE maker = 'A'
```

## 14

https://sql-ex.ru/learn_exercises.php?LN=14

```sql
SELECT Classes.class, Ships.name, Classes.country
FROM Ships
JOIN Classes ON Ships.class = Classes.class
WHERE numGuns >=10
```

## 15

https://sql-ex.ru/learn_exercises.php?LN=15

```sql
SELECT hd 
FROM PC 
GROUP BY (hd)
HAVING COUNT(model) >= 2
```

## 16

https://sql-ex.ru/learn_exercises.php?LN=16

```sql
SELECT DISTINCT p1.model, p2.model, p1.speed, p1.ram
FROM PC AS p1, PC AS p2
WHERE p1.speed = p2.speed AND p1.ram = p2.ram AND p1.model > p2.model
```

## 17

https://sql-ex.ru/learn_exercises.php?LN=17

```sql
SELECT DISTINCT Product.type, Laptop.model, Laptop.speed
FROM Laptop, Product
WHERE speed <
(SELECT MIN(speed) FROM PC) AND Product.type='Laptop'
```

## 18

https://sql-ex.ru/learn_exercises.php?LN=18

```sql
SELECT DISTINCT maker, price
FROM Printer
JOIN Product ON Product.model = Printer.model
WHERE color = 'y'
AND price = (SELECT MIN(price) FROM Printer WHERE color = 'y')
```

## 19

https://sql-ex.ru/learn_exercises.php?LN=19

```sql
SELECT DISTINCT maker, AVG(screen)
FROM Laptop
JOIN Product ON Laptop.model = Product.model
GROUP BY maker
```

## 20

https://sql-ex.ru/learn_exercises.php?LN=20

```sql
SELECT maker, COUNT(model)
FROM Product
WHERE type = 'PC'
GROUP BY maker
HAVING COUNT (model) >= 3
```
