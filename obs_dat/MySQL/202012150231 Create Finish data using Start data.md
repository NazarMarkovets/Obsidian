#MYSQL 

##### Взять данные начала заказа и вставить их в дату конца, прибавив 3 дня
```sql
update inno.order set order_done = DATE_ADD(order_start, INTERVAL 3 DAY);
```
