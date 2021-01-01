#MYSQL 

Процедура (Stored Procedure) – це
іменований програмний об’єкт СУБД, написаний мовою SQL, що становить
собою загальний виконуваний ресурс для всіх баз даних. Код збереженої
процедури (ЗП) зберігається, компілюється й виконується на стороні сервера.

Якщо програмний додаток використовує процедуру (функцію), то
спочатку вона компілюється, поміщається в пам’ять і відпрацьовується як
запит. Запит кешується. Під час повторного звернення в одному з’єднанні
(сесії) використовується її кешована версія. Процедури можуть викликатися з
процедур, функцій і інших типів програмних об’єктів. Мета застосування
процедур і функцій – підвищення ефективності роботи з даними, шляхом
багаторазового використання повторюваного коду.



##### Использование зарезервированого оператора
```sql
DECLARE total_products IND DEFAULT 0
SELECT COUNT(1) INTO total_products
FORM products
```

Для присвоения значения переменной используют оператор SET. 


##### присвоения значения переменной
```sql
DECLARE total_products IND DEFAULT 0
SET total_products = 10;
```



<mark>Про переменные:</mark>
> Каждая переменная имеет свою область видимости, определяющую время ёё жизни.
> Если создать переменную внутри зранимой процедуры, то она будет существовать, пока используется.
> Если декларировать переменную внутри блока BEGING... END, то она будет существовать в пределах этого блока.
> Переменные со знаком `@` вначале названия являются <u>глобальными</u> они доступны на протяжении всей сессии.



##### Процедура с параметрами
```sql
CREATE PROCEDURE getStudentInfo(IN s_name VARCHAR(64))
BEGIN 
   SELECT * FROM student_database.student s where s.sname = s_name;
END; 
```


##### Call the procedure
```sql
CAll getStudentInfo('pass_required_name');
```


>Создать хранимую процедуру, которая выведет продавцов, оформивших заказы, по диапазонам. Если аргумент имеет значение «Маленькая суммы», то диапазон продаж от 0 до 1000, «Средние суммы» — от 1000 до 1500, «Большие суммы» — свыше 1500.
>
##### IF-else, case, while
```sql
DELIMITER //
CREATE PROCEDURE get_salespeople(str VARCHAR(45))
BEGIN
    CASE str
    WHEN "Маленькие суммы"
    THEN
        SELECT sname as "Имя продавца", SUM(amt) as "Суммарные продажи"
        FROM salespeople
        INNER JOIN orders on salespeople.snum = orders.snum
        group by sname
        HAVING SUM(amt) < 1000;
    WHEN "Средние суммы"
    THEN
        SELECT sname as "Имя продавца", SUM(amt) as "Суммарные продажи"
        FROM salespeople
        INNER JOIN orders on salespeople.snum = orders.snum
        group by sname
        HAVING SUM(amt) >= 1000 and SUM(amt) < 1500;
    WHEN "Большие суммы"
    THEN
        SELECT sname as "Имя продавца", SUM(amt) as "Суммарные продажи"
        FROM salespeople
        INNER JOIN orders on salespeople.snum = orders.snum
        group by sname
        HAVING SUM(amt) >= 1500;
    END CASE;
END //
DELIMITER ;
```


[Procedure](https://codetown.ru/sql/hranimye-procedury/)