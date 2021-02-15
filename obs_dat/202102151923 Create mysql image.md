#Docker 
##### Creating example
```
docker run --name comments  -e MYSQL_ROOT_PASSWORD=password -d mysql:8.0.23
```
where:
`comments` - name of image
`password` - pass that will be used
`:8.0.23` - version

# Next

##### Text
```bash
docker exec -it comments bash
```

`comments` - name of image

# Connect to server

##### Text
```bash
mysql -u root -ppassword
```

Don't paste `space` between -p and `password`(current password for server) 