#MYSQL 

#
<div align="center">
<span class='flair' style='background-color:#F1C40F;color:#000;margin:5px'>
Learning
</span>
<img width="20" height="20" src="https://www.flaticon.com/svg/static/icons/svg/945/945147.svg">
</div>

<hr>

# Code

##### Text

```sql

update innodb.driver
set Birth_Date = replace(Birth_Date, '\.', '\-')
where Driver_ID > 0;

update innodb.driver SET Birth_Date = str_to_date(Birth_Date, "%d-%m-%Y")
where Driver_ID>0;

```



##### update example
```sql
update inno.user set email = (replace (email, 'gmail.com','@gmail.com'));
```
