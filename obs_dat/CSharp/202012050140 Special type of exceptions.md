- `DivideByZeroException`: представляет исключение, которое генерируется при делении на ноль

- `ArgumentOutOfRangeException`: генерируется, если значение аргумента находится вне диапазона допустимых значений

- `ArgumentException`: генерируется, если в метод для параметра передается некорректное значение

- `IndexOutOfRangeException`: генерируется, если индекс элемента массива или коллекции находится вне диапазона допустимых значений

- `InvalidCastException`: генерируется при попытке произвести недопустимые преобразования типов

- `NullReferenceException`: генерируется при попытке обращения к объекту, который равен null (то есть по сути неопределен)


##### Text
```dotnet
catch (DivideByZeroException)
    {
        Console.WriteLine("Возникло исключение DivideByZeroException");
    }
    catch (IndexOutOfRangeException ex)
    {
        Console.WriteLine(ex.Message);
    }
```

<mark>Когда в блоке try возникнет исключение, то CLR будет искать нужный блок catch для обработки исключения.</mark>

А определять для всех типов исключений блоки catch, если обработка исключений однотипна, не имеет смысла. И в этом случае мы можем определить блок catch для базового типа Exception:


##### Text
```dotnet
try
    {
        object obj = "you";
        int num = (int)obj;     // InvalidCastException
        Console.WriteLine($"Результат: {num}");
    }
    catch (DivideByZeroException)
    {
        Console.WriteLine("Возникло исключение DivideByZeroException");
    }
    catch (IndexOutOfRangeException)
    {
        Console.WriteLine("Возникло исключение IndexOutOfRangeException");
    }
    catch (Exception ex)
    {
        Console.WriteLine($"Исключение: {ex.Message}");
    }  
    Console.Read();
```

При этом блоки catch для более общих, более базовых исключений следует помещать в конце - после блоков catch для более конкретный, специализированных типов. Так как CLR выбирает для обработки исключения первый блок catch, который соответствует типу сгенерированного исключения. Поэтому в данном случае сначала обрабатывается исключение DivideByZeroException и IndexOutOfRangeException, и только потом Exception (так как DivideByZeroException и IndexOutOfRangeException наследуется от класса Exception).