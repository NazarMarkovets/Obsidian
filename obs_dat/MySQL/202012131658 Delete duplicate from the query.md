

#MYSQL 
<div align="center">
<span class='flair' style='background-color:#F1C40F;color:#000;margin:5px'>
Learning MySQL
</span>
<img width="20" height="20" src="https://www.flaticon.com/svg/static/icons/svg/945/945147.svg">
</div>

<hr>



##### SqL
```sql
select 
	distinct order_id 
from 
	inno.order,
	inno.order_services 
where order_id = fk_order_id
```
