#MYSQL 

#
<div align="center">
<span class='flair' style='background-color:#F1C40F;color:#000;margin:5px'>
Learning
</span>
<img width="20" height="20" src="https://www.flaticon.com/svg/static/icons/svg/945/945147.svg">
</div>

<hr>

# Select instructions

Table for example:

![[select statement.png]]

# <u>Remarks</u>
If you need to use name of DB do like this `db.table`

## <u>AS</u>
To rename column name only in query use `as`
> col_name `AS` new_name
> ==Attention==
> It is not recommended to use `as` in SQL statements 
 
##### for pseudonyms do like:
```sql
SELECT nameUser name, idUser ID
FROM `mu`.`user`;
``` 

![[Select result.png]]

# Some selects together

![[Some selects together.png]]