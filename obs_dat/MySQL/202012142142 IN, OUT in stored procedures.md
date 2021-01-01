#MYSQL 

В случаях, когда у вас в результате выполнения процедуры необходимо вернуть единичные значения удобнее использовать выходные параметры, а не набор данных. Это упрощает манипулирование выходными данными за пределами процедуры.

Пример процедуры с выводом набора данных:


##### Text
```sql
DELIMITER \\

CREATE PROCEDURE p_dataset (IN id INT)
BEGIN
   IF id >= 10 THEN INSERT SELECT 1 as res;
   ELSE SELECT 0 as res;
   END IF;
END\\

DELIMITER ;

CALL p_dataset (11);

DROP PROCEDURE p_dataset;
```

В данном случае вы всегда получите набор данных с одной строкой. Для дальнейшего манипулирования полученным значением, необходимо совершить дополнительные действия с выводимым процедурой набором данных.

Вариант с выходным параметром, напротив, дает вам на выходе конкретную переменную (или переменные), которую дальше можно сразу использовать вне процедуры:


##### Text
```sql
DELIMITER \\

CREATE PROCEDURE p_out (IN id INT, OUT result INT)
BEGIN
    IF id >= 10 THEN SET result = 1;
    ELSE SET result = 0;
    END IF;
END\\

DELIMITER ;

CALL p_out (1, @res_out); --call procedure

SELECT @res_out; -- получение значения глобальной переменной после изменений в процедуре		

DROP PROCEDURE p_out;
```

