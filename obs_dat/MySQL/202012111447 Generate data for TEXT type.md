#MYSQL 

Если нужно заменить одинаковые текстовые строки на рандомные значения
необходимо выполнить update  для этого столбца:

##### Text
```sql
UPDATE `my`.`user` SET `History` =

(select concat(
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0)
    
) as rnd_str_32);

```




##### Если нужно вставить пробелы 
```sql
UPDATE `my`.`user` SET `History` =

(select concat(
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    ' ',
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    ' ',
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    ' ',
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    ' ',
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    ' ',
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    ' ',
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    ' ',
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    ' ',
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0),
    ' ',
    lpad(conv(floor(rand()*pow(36,8)), 10, 36), 8, 0)
    
) as rnd_str_32);
```