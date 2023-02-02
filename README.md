# MySQL

# Задание:
## Предусловия: установите MySQL Server и MySQL Workbench (версию ниже 8.20)

## Наша задача разобраться с простыми и немного усложненными запросами к базам данных, написанных на  SQL

## Скачайте дампы базы данных Hogwarts отсюда https://drive.google.com/drive/u/3/folders/1MC0AttnmlAmugifFlX3hG6pssYZDqpPB
## Осуществите импорт таблиц, используя Workbench
## Выполните задание 1 и 2, которые вы найдете здесь https://drive.google.com/drive/u/3/folders/1Lt7CY69nR5awNs_9q0XJOHRti4vJj3Qa
## Сохраните свое решение в виде документа Word, куда необходимо добавить скрины отправленных запросов в CLI или Workbench

## Помните, что большинство ошибок возникает из-за неправильного синтаксиса и использования операторов. Будьте внимательные. Проверяйте результаты, отправленных запросов, чтобы быть уверенным в своем решении

# Задание 1.
## 1.	Выведите имя, фамилию, патронуса всех персонажей, у которых есть patronus или он известен:
## SELECT fname, lname, patronus FROM characters 
##	    WHERE NOT patronus = 'Unknown' OR patronus IS NOT NULL;
 
![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-1.png)

## 2.	Выведите фамилию персонажей, у которых последняя буква в фамилии ‘e’ 
## SELECT lname FROM characters 
## 	WHERE lname LIKE '%e'; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-2.png)


## 3.	Посчитайте общий возраст всех персонажей и выведите это на экран 
## SELECT SUM(age) FROM characters; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-3.png)

## 4.	Выведите имя, фамилию и возраст персонажей по убыванию их возраста
## SELECT fname, lname, age FROM characters
## 	ORDER BY age DESC; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-4.png)

## 5.	Выведите имя персонажа и возраст, у которых последний находится в диапазоне от 50 до 100 лет 
## SELECT lname, age FROM characters 
## 	WHERE age BETWEEN 50 AND 100; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-5.png)

## 6.	Выведите возраст всех персонажей так, чтобы среди них не было тех, у кого он одинаковый 
## SELECT DISTINCT age FROM characters; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-6.png)

## 7.	Выведите всю информацию о персонажах, у которых faculty = Gryffindor и чей возраст больше 30 лет 
## SELECT * FROM characters 
## WHERE faculty = 'Gryffindor' AND age >30; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-7.png)

## 8.	Выведите имена первых трех факультетов из таблицы, так чтобы факультеты не повторялись
## SELECT DISTINCT faculty FROM characters
## LIMIT 3;

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-8.png)

## 9.	 Выведите имена всех персонажей, у которых имя начинается с ‘H’ и состоит из 5 букв, или чье имя начинается с ‘L’ 
## SELECT fname FROM characters 
## WHERE fname LIKE 'H____' OR fname LIKE 'L%'; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-9.png)

## 10.	Посчитайте средний возраст всех персонажей 
## SELECT AVG(age) FROM characters; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-10.png)

## 11.	 Удалите персонажа с ID = 11 
## DELETE FROM characters 
## WHERE char_id = 11; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-11.png)

## 12.	Выведите фамилию всех персонажей, которые содержат в ней букву ‘a’ 
## SELECT lname FROM characters 
## WHERE lname LIKE '%a%'; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-12.png)

## 13.	Используйте псевдоним для того, чтобы временно замените название столбца fname на Half-Blood Prince для реального принца-полукровки 
## SELECT fname as Half_Blood_Prince FROM characters 
## WHERE fname = 'Severus'; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-13.png)


## 14.	Выведите id и имена всех патронусов в алфавитном порядки, при условии, что они есть или известны
## SELECT char_id, patronus FROM characters
## WHERE NOT patronus = 'Unknown' AND patronus IS NOT NULL
## ORDER BY patronus ASC; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-14.png)

## 15.	Используя оператор IN, выведите имя и фамилию тех персонажей, у которых фамилия Crabbe, Granger или Diggory 
## SELECT fname, lname FROM characters 
## WHERE lname IN ("Crabbe", "Granger", "Diggory"); 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-15.png)

## 16.	Выведите минимальный возраст персонажа 
## SELECT MIN(age) FROM characters; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-16.png)

## 17.	Используя оператор UNION выберите имена из таблицы characters и названия книг из таблицы library
## SELECT fname FROM characters 
## UNION
## SELECT book_name FROM library; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-17.png)

## 18.	Используя оператор HAVING посчитайте количество персонажей на каждом факультете, оставив только те факультеты, где количество студентов больше 1 
## SELECT faculty, COUNT(faculty) FROM characters 
## GROUP BY faculty
## HAVING COUNT(faculty) > 1; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-18.png)

## 19.	Используя оператор CASE опишите следующую логику:
## Выведите имя и фамилию персонажа, а также следующий текстовое сообщение:

## Если факультет Gryffindor, то в консоли должно вывестись Godric
## Если факультет Slytherin, то в консоли должно вывестись Salazar
## Если факультет Ravenclaw, то в консоли должно вывестись Rowena
## Если факультет Hufflepuff, то в консоли должно вывестись Helga
## Если другая информация, то выводится Muggle
## Для сообщения используйте псевдоним Founders
## SELECT fname, lname,  
## CASE 
## 		WHEN faculty = "Gryffindor" THEN "Godric" 
## WHEN faculty = "Slytherin" THEN "Salazar"
## WHEN faculty = "Ravenclaw" THEN "Rowena"
## WHEN faculty = "Hufflepuff" THEN "Helga" 
## ELSE "Muggle"
## END AS "Founders"
## FROM characters; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-19.png)

## 20. Используя регулярное выражение найдите фамилии персонажей, которые не начинаются с букв H, L или S и выведите их 
## SELECT lname FROM characters 
## WHERE NOT lname REGEXP '^[HLS]'; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/1-20.png)

# Задание 2.
## 1.	Выведите имя, фамилию персонажей и название книги, которая на них числится 
## SELECT fname, lname, book_name FROM characters
## INNER JOIN library ON characters.char_id = library.char_id;

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/2-1.png)

## 2.	Выведите имя, фамилию персонажей и название книги, вне зависимости от того, есть ли у них книги или нет 
## SELECT fname, lname, book_name FROM characters
## RIGHT JOIN library ON characters.char_id = library.char_id;

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/2-2.png)

## 3.	Выведите название книги и имя патронуса, вне зависимости от того, есть ли информация о держателе книги в таблице или нет 
## SELECT fname, lname, book_name FROM characters
## RIGHT JOIN library ON characters.char_id = library.char_id; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/2-3.png)

## 4.	Выведите имя, фамилию, возраст персонажей и название книги, которая на них числится, при условии, что все владельцы книг должны быть старше 15 лет 
## SELECT fname, lname, age, book_name FROM characters
## INNER JOIN library ON characters.char_id = library.char_id
## WHERE age > 15; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/2-4.png)

## 5.	Выведите имя персонажа, название книги, дату выдачи и дату завершения, при условии, что он младше 15 лет и его патронус неизвестен 
## SELECT fname, book_name, start_date, end_date FROM characters
## INNER JOIN library ON characters.char_id = library.char_id
## WHERE age < 15 AND patronus = "Unknown"; 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/2-5.png)

## 6.	Используя вложенный запрос количество книг, у которых end_date больше, чем end_date у Hermione
## SELECT count(book_id) FROM library
## WHERE end_date > (SELECT end_date FROM library
## WHERE char_id = 2); 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/2-6.png)

## 7.	С помощью вложенного запроса выведите имена всех патронусов, у которых владельцы старше возраста персонажа, у которого патронус Unknown
## SELECT patronus FROM characters
## WHERE age > (SELECT age FROM characters
## WHERE patronus = 'Unknown'); 

![Header](https://github.com/ViacheslavQApro/sql/blob/master/images/2-7.png)

## THE END 
