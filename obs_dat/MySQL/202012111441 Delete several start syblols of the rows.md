#MYSQL 

Если нужно обрезать уже созданные 4000 значений в таблице типа  TEXT, VARCHAR....

##### Cut the row
```sql
UPDATE `my`.`user` SET `History` = SUBSTR(`History`,8);
```