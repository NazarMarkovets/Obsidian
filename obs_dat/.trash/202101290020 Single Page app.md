

## Tasks 
- [ ] Писать и получать запросы из сервера на JS
- [ ] Научиться отправлять и получать его асинхронно
- [ ] java script promice

[Работа с сервером ](https://developer.mozilla.org/ru/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data)


Ошибка 
>Uncaught SyntaxError: Unexpected end of JSON input at JSON.parse 
	
Возможно ссылка на решение
	https://stackoverflow.com/questions/51118396/uncaught-syntaxerror-unexpected-end-of-json-input-at-json-parse-anonymous
	
### Проблема в строке 

##### Text
```js
JSON.parse(request.responseText);
```

Как решение определить переменную принимающую значение request.responseText чтобы оно не было пустым в момент парса.
	
	
Возможно нужно писать создание параграфов прям в теле функции

![[Pasted image 20210130010305.png]]

где InnerHTML


https://msiter.ru/tutorials/javascript/js_json_php