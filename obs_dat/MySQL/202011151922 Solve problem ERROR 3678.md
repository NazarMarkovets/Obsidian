#MYSQL 

<div align="center">
<span class='flair' style='background-color:#F1C40F;color:#000;margin:5px'>
3678
</span>
<img width="20" height="20" src="https://www.flaticon.com/svg/static/icons/svg/945/945147.svg">
</div>

It becomes when you try create new schema with the same name
For example you had schema with name `test` and you've deleted it, after some time you can decided to create a schema with name `test` again. 

#### Solving:
1. Go to path where is main data of your server
	For example:
	```sql
	C:\ProgramData\MySQL\MySQL Server 8.0\Data
	```

2. Try to find the folder with name of the scheme you've deleted before
3. Delete that folder
4. Try to create scheme again!
