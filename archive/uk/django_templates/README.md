# Django шаблони

Час вивести деякі дані! Django надає нам певні допоміжні, вбудовані __шаблонні теги__ для цього.

## Що таке шаблонні теги?

Як бачите, в HTML, ви не можете помістити Python код, тому що браузери не зрозуміють його. Вони знають лише HTML. Ми знаємо, що HTML більшою мірою є статичною, в той час як Python є більш динамічною мовою.

__Шаблонні теги Django__ дозволяють нам передавати Python-подібні речі в HTML, таким чином можна розробляти динамічні веб-сайти швидше і простіше. Ой!

## Шаблон для виведення списку постів

В попередньому розділі ми надали нашому шаблону список постів у змінній `posts`. А тепер відобразимо це в HTML.

Щоб надрукувати змінну в Django шаблоні, ми використовуємо подвійні фігурні дужки з іменем змінної всередині:

```html
{{ posts }}
```

Спробуйте це в шаблоні `blog/templates/blog/post_list.html`. Починаючи з другого `<div>` до третього `</div>` замініть все на `{{ posts }}`. Збережіть файл і оновіть сторінку, щоб побачити результат:

![Рисунок 13.1](images/step1.png)

Як можна побачити, все що ми отримали, це:

    <QuerySet [<Post: My second post>, <Post: My first post>]>

Означає, що Django розуміє це як список об'єктів. Пам'ятаєте із розділу __Вступ до Python__ як ми можемо виводити списки? Звичайно, за допомогою циклу __for__! У Django шаблонах ви можете створити їх наступним чином:

```html
{% for post in posts %}
    {{ post }}
{% endfor %}
```

Спробуйте це у вашому шаблоні.

![Рисунок 13.2](images/step2.png)

Працює! Однак, бажано, щоб вони були виведені як статичні пости, які ми створили раніше у розділі __Вступ до HTML__. Ви можете компонувати теги HTML і шаблонні теги. Наша частина `body` буде виглядати так:

```html
<div>
    <h1><a href="/">Django Girls Blog</a></h1>
</div>

{% for post in posts %}
    <div>
        <p>published: {{ post.published_date }}</p>
        <h1><a href="">{{ post.title }}</a></h1>
        <p>{{ post.text|linebreaksbr }}</p>
    </div>
{% endfor %}
```

{% raw %}Все, що ви напишете між `{% for %}` та `{% endfor %}` повторюватиметься для кожного об'єкта у списку. Оновіть сторінку:{% endraw %}

![Рисунок 13.3](images/step3.png)

Чи помітили ви, що цього разу ми використали трохи відмінні позначення `{{ post.title }}` або `{{ post.text }}`? Ми маємо доступ до даних, що містяться в кожному полі, визначеному в нашій моделі `Post`. Також `|linebreaksbr` перенаправляє текст посту через фільтр щоб конвертувати розриви ліній в абзаци.


## Ще одне

Було б непогано побачити як ваш сайт буде працювати в інтернеті, так? Давайте спробуєм розгорнути його в PythonAnywhere знову. Ось наступні кроки...

*   По-перше, залийте ваш код на Github

```
$ git status
[...]
$ git add --all .
$ git status
[...]
$ git commit -m "Modified templates to display posts from database."
[...]
$ git push
```

*   Потім, увійдіть до [PythonAnywhere](https://www.pythonanywhere.com/consoles/) та перейдіть до **Bash консолі** (або запустіть нову) і виконайте команди:

```
$ cd my-first-blog
$ git pull
[...]
```

* Нарешті, перейдіть на вкладку [Web](https://www.pythonanywhere.com/web_app_setup/) і натисніть **Reload** (перезавантажити) у веб-додатку.


Вітаємо! А тепер спробуйте додати новий пост у вашому Django адміністраторі (не забудьте додати published_date!), потім перезавантажте сторінку, щоб переконатись, чи з'явився новий пост.

Все працює, як годинник? Ми пишаємося! Відійдіть ненадовго від комп'ютера, ви заслуговуєте на перерву. :)

![Рисунок 13.4](images/donut.png)