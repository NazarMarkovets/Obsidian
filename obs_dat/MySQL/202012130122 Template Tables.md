

#MYSQL 
<div align="center">
<span class='flair' style='background-color:#F1C40F;color:#000;margin:5px'>
Learning MySQL
</span>
<img width="20" height="20" src="https://www.flaticon.com/svg/static/icons/svg/945/945147.svg">
</div>

<hr>



####  Creating an empty template table
```sql
CREATE TEMPORARY TABLE `tmp_table` (
	`id` int(11) unsigned NOT NULL AUTO_INCREMENT,
	`name` varchar(255) NOT NULL,
	`price` decimal(11,2) unsigned NOT NULL DEFAULT '0.00',
	`sef` varchar(255) NOT NULL,
	`text` text NOT NULL,
	`approve` tinyint(1) NOT NULL DEFAULT '1',
	`date_add` int(11) unsigned NOT NULL DEFAULT '0',
	PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8 AUTO_INCREMENT=1
```


#### Creating a table using the structure of other table
```sql
CREATE TEMPORARY TABLE `tmp_table` LIKE `prods`
```


#### Cloning a table
```sql
CREATE TEMPORARY TABLE `tmp_table` 
	SELECT * FROM  `prods`
```


#### Create table and cloning from several tables
```sql
CREATE TEMPORARY TABLE `tmp_table` 
	SELECT 
		`prods`.`name`,
		`urls`.`sef`
	FROM 
		`prods`
	LEFT JOIN 
		`urls`
	ON
		`prods`.`id` = `urls`.`prods_id`
	WHERE
		`prods`.`approve` = 1
```


#### Work with template tables
```sql
-- Adding data
INSERT INTO `tmp_table` SET `name` = 'Запись 1', `approve` = 1, `date_add` = UNIX_TIMESTAMP();
 
-- Изменение
UPDATE `tmp_table` SET `approve` = 0 WHERE `id` = 1;
 
-- Удаление
DELETE FROM `tmp_table` WHERE `approve` = 0;
 
-- Выборка
SELECT * FROM `tmp_table` WHERE `approve` = 1;

```


[[SQLManual]]