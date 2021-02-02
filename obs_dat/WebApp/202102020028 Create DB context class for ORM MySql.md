#WebApp 

При создании сервиса, который использует ORM для управления данными БД на основе Mysql необходимо добавить NuGET package 
`Pomelo.EntityFrameforkCore.Mysql`


##### Add class 
```dotnet

using System;  
using Microsoft.EntityFrameworkCore;  
using System.Threading.Tasks;  
using System.Collections;  
using WebApplication.Models;  
  
namespace WebApplication.Db  
{  
 public class AppDatabaseContext: DbContext  
 {  
 public AppDatabaseContext(DbContextOptions<AppDatabaseContext\> options): base(options){}  
 public DbSet<Article> article { get; set; }  
 public DbSet<Author> author { get; set; }    
public AppDatabaseContext()  
 { 
 	Database.EnsureCreated();  
 } 
 protected override void OnConfiguring(
 						DbContextOptionsBuilder optionsBuilder)  
 =>optionsBuilder.UseMySql(
 "server=localhost;database=everlastingblog;uid=root;password=warKrawT228787898787899;",
 new MySqlServerVersion(new Version(8, 0, 21)));  
           
     
    }  
}

```

