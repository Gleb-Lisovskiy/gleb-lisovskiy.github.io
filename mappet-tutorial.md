---
layout: default
---

# Внимание

**Данный туториал находится в раннем разработке!  
Могут быть ошибки или опечатки!  
Помогите улучшить данный туториал.**  
Спасибо, что прочитали.

# Mappet Туториал по программировании (Только JavaScript) 

Здраствуйте я Glebun08 и cегодня научу вас кодить в моде для Майнкрафта **Mappet**.  
Этот гайд для тех, кто хочет научится только основы Mappet'а Javascript'а

Если у вас возникли вопросы или идеи, задайте [тут](https://t.me/Glebun08)

* Рекомедуется для новичка
    - Знание английского (без этого, будет сложно программировать)
    - Немного терпение (Многие программисты включая меня, могут часто делать проблемы или ошибки в своих скриптах, так что будьте готовы в будущем терпеть и исправлять)
    - Поддержка от друга или программиста (**Этот пукнт необязателен**, но желательно чтобы вы не сошли с ума)

## Первая глава: Создание скрипта

После того когда вы установили мод Mappet и языковой движок Nashorn (JavaScript), создайте или зайдите в любой мир, который в нём будете программировать.

После того когда вы зашли в мир, нажмите клавишу = (Не на доп. панели).

После  этого, вы попадайте в меню маппета и во вкладке "**Настройки сервера**",  
К этой вкладке мы еще вернёмся, но нам нужно перейти на вкладку "**Скрипты**"  
![img]({{ site.base_url }}/assets/img/screenshot1.png)

Теперь создайте скрипт, нажав плюс справа сверху.
![img]({{ site.base_url }}/assets/img/screenshot2.png)

Называйте скрипт как хотите и жмите Ок.  

## Вторая глава: Скриптинг

После того когда вы создали скрипт, в скрипте видите это:

```javascript
function main(c)
{
    // Code...
    var s = c.getSubject();
}
```

Первым чем я хочу познакомить это код "**function**",  
Она является основным частью кода и всё что находится в внутри скобках, запускается.

Перед кодом function, написано main это название function'а.  
Оставьте main, чтобы скрипт запускался по обычному.  
С этим мы потом еще разберёмся.

А сейчас познакомлю вас с переменными.
По сути, с помощью их можно сокращать большой код в одно слово.

--

Существует три способа объявления переменных в JavaScript: с помощью ключевых слов var, let и const:

- var. Используется для объявления переменных с функцией или глобальной областью видимости. Переменные, объявленные с помощью var, могут быть переопределены и повторно объявлены.
- let. Позволяет объявлять переменные с блочной областью видимости. Переменные, объявленные с помощью let, могут быть переопределены, но не могут быть повторно объявлены в той же области видимости.
- const. Применяется для объявления констант, то есть данных, которым нельзя присвоить новое значение. (Но в маппете не будем использовать.)

Имя переменной должно начинаться с буквы, символа подчёркивания (_) или знака доллара ($). Оно не может содержать пробелов или специальных символов, кроме подчёркивания и доллара.

Переменные можно объявлять без ключевых слов let, var или const, но такой способ не рекомендуется, так как это может привести к нежелательным эффектам и ошибкам.

-- YandexGPT

Ну или проще говоря

- var. Это переменна который работает даже за пределами скобками, к примеру function.
- let. Тоже самый var, только работает внутри скобках, к примеру function.

А вот const я даже не знаю как использовать его, но оно нам не нужен в туториале.

С переменными мы разобрались, а теперь с кодами маппета и другие.

Основные коды:

- getSubject. Этот код берёт субъекта или к примеру берёт того, кто запустил скрипт.
- getStates. Этот код берёт статы сущности или сервера.
- getPosition. Этот код берёт позицию сущности.

### **Важно**

Когда вы водите код к примеру getSubject
Нужно всегда писать в начале "**c.**" (Если в function есть (a) вместо "**c**", то значит писать "**a**").  
А потом сам же код и писать (Без пробелов) скобки после кода ()

---

Пример скрипта 1:

```javascript
function main(c) 
{
    var s = c.getSubject(); // Берёт субъект/сущность
    if (s.isSprinting()) // Если сущность бежит
    {
        s.kill(); // Убивает сущность
    }
}
```

Пример скрипта 2:

```javascript
function main(c) 
{
    var s = c.getSubject(); // Берёт субъект/сущность
    var pos = s.getPosition(); // Берёт позицию
    if (s.isSneaking()) // Если сущность крадется
    {
        s.setPostion(pos.x, pos.y + 5, pos.z); // Телепортирует сущность на 5 блоков выше  
        // Вместо "pos.x", pos.y" и "pos.z".
        // Можно заменить числами координат к примеру 100 500 100
    }
}
```

Пример скрипта 3:

```javascript
function main(c) 
{
    var s = c.getSubject(); // Берёт субъект/сущность
    var states = s.getStates(); // Берёт статы
    if (!s.isSprinting()) // Если сущность не бежит
    {
        states.setNumber("IsSprinting", 0); // Приминяет стату на 0
    } else // Если нет
    {
        states.setNumber("IsSprinting", 1); // Приминяет стату на 1
    }
}
```
