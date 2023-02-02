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
(https://github.com/ViacheslavQApro/sql/blob/master/images/1-1.png) 

