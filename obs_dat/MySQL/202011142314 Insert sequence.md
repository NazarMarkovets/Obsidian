#MYSQL 

It is so important to have the right sequence of inserts
For example we have a scheme:
![[InnoDB in IDEF1X.png]]

It means that we should make a special sequence as:
```code
┌─  role
├─► user
├─► status
├─► order
├─► format_type
├─► macket_to_print
├─► order_macket
├─► fonts
├─► paper_density
├─► paper_brightness
├─► paper_iso
├─► paper_colors
├─► paper_covering
├─► paper
├─► services
└─► order_services
```




##### Код необходимый для быстрого создания записей на ввод
```sql
INSERT INTO user(name, email, phone)

SELECT 
	CONCAT(name, lpad(conv(floor(rand()*pow(36,6)),10, 36), 6, 0)) as name
	email,
	CONCAT(LEFT(phone,8), ROUND(RAND()*100)) as phone

```
