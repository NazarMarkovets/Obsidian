#MYSQL 

Is used for denormalized table if we need to put value from normalized table to  value in the denormalized table. Look at the example below.

##### replace format name from inno.format_type_name to dmy.format_type
```sql

UPDATE dmy.macket_to_print 
SET 
    format_type = (SELECT 
            name
        FROM
            (SELECT 
                inno.macket_to_print.macket_id AS id,
                    inno.format_type.format_type_name AS name
            FROM
                inno.macket_to_print
            INNER JOIN inno.format_type ON inno.format_type.format_type_id = inno.macket_to_print.fk_macket_to_formatType) AS id_to_name
        WHERE
            id = dmy.macket_to_print.macket_id);
			
```
