# `Домашнее задание к занятию 12.3 "SQL. Часть 1"` - `Наталья Мартынова (Пономарева)`

### Задание 1

```
select distinct district
from address 
where district like 'K%a' and district = REPLACE(district, ' ', '')
```
### Задание 2

```
select payment_id, customer_id, staff_id, rental_id, amount, date(payment_date), date(last_update) 
from payment p 
where (date(payment_date) BETWEEN '2005-06-15' AND '2005-06-18')
order by date(payment_date)
```
### Задание 3

```
select * from rental r order by rental_date desc limit 5
```
### Задание 4

```
select lower(first_name), last_name, email, replace(lower(first_name),'ll','pp')
from customer c 
where lower(first_name) like 'Kelly' or lower(first_name) like 'Willie'
```
### Задание 5

```
select first_name, last_name, substring_index(email,'@',1), substring_index(email,'@',-1) 
from customer c 
```
### Задание 6

```
select CONCAT(UCASE(MID(first_name,1,1)),LCASE(MID(first_name,2))), 
CONCAT(UCASE(MID(last_name,1,1)),LCASE(MID(last_name,2))), 
CONCAT(UCASE(MID(last_name,1,1)),LCASE(MID(substring_index(email,'@',1),2))), 
substring_index(email,'@',-1)  
from customer
```
