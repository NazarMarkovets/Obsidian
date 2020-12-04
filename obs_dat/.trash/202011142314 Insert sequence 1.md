#MYSQL 

It is so important to have the right sequence of inserts
For example we have a scheme:

![[photo_2020-11-16_15-24-43.jpg]]

It means that we should make a special sequence as:
```code

┌─  category
├─► driver
├─► category_driver
├─► truck
├─► gender
├─► role
├─► user
├─► status
├─► driver_truck
├─► order
```