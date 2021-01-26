#Csharp 

<u>AND</u> is only `true` when both sides are true:
T && T = true;
T && F = false
F && F = false;
F && T = false;

<u>OR </u> || is also used
It is true even one of sides is true

T || T = true
T || F = true
F || T = true
F || F = false

Случаи в условии


##### operators priority
```dotnet
if (age > 18 || age < 65 && rating == 'G')

```
В этом случае будет сравнение 
`(age > 18) || (age < 65 && rating == 'G')`