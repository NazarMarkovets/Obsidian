#MYSQL 

Можно использовать конструкцию insert с использованием select которая
производит записи в количестве равному геомертрической прогрессии
##### code 
```sql
insert into users(name, email, phone)

select 
	concat (name, lpad(conf(floor(rand()*pow(36,6)), 10, 36), 6, 0)) as name,
	email,
	concat (LEFT(phone, 8) ROUND(RAND() * 100)) as phone
from 
	users
```
