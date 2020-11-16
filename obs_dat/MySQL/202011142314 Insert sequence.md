#MYSQL 

It is so important to have the right sequence of inserts
For example we have a scheme:
![[InnoDB in IDEF1X.png]]

It means that we should make a special sequence as:
```code
┌─ user_role
├─► user
├─► order_status
├─► order
├─► format_type
├─► macket_to_print
├─► order_macket
├─► fonts
├─► paper_density
├─► paper_brightness
├─► paper
├─► services
└─► order_services
```