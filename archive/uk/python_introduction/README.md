# Вступ до Python

> Частина цього розділу базується на матеріалах Geek Girls Carrots (https://github.com/ggcarrots/django-carrots).

Давайте напишемо якийсь код!

## Командний рядок Python

Щоб розпочати роботу із Python, нам необхідно відкрити *командний рядок*. Ви вже повинні знати як це зробити, адже ознайомились із цим у розділі [Вступ до командного рядка](../intro_to_command_line/README.md).

Як тільки будете готові, виконайте наведені нижче інструкції.

Ми хочемо відкрити консоль Python, тому введіть `python` на Windows або `python3` на Mac OS/Linux та натисніть `Enter`.

    $ python3
    Python 3.4.3 (...)
    Type "help", "copyright", "credits" or "license" for more information.
    >>>

## Ваша перша команда на Python!

Після запуску команди Python командний рядок зміниться на `>>>`. Для нас це означає, що відтепер ми можемо користуватися лише командами мови Python. Вам не доведеться друкувати `>>>` - Python зробить це для вас сам.

Якщо забажаєте вийти із консолі Python, просто наберіть `exit()` або використайте комбінацію `Ctrl + Z` для Windows і `Ctrl + D` для Mac/Linux. Після того ви більше не побачите `>>>`.

Але наразі, ми не бажаємо виходити із консолі Python. Ми хочемо дізнатися про неї більше. Почнемо з чогось простенького. Наприклад, спробуйте виконати певні алгебраїчні операції, на зразок `2 + 3` та натисніть `enter`.

    >>> 2 + 3
    5

Чудово! Бачите, яким чином здійснено вивід відповіді? Python знає математику! Можна спробувати інші команди, наприклад:
- `4 * 5`
- `5 - 1`
- `40 / 2`

Поки що можете трохи побавитися із математикою, а далі повертайтесь назад :).

Як бачите, Python є чудовим калькулятором. Хіба вас не цікавить, що ще можна робити...

## Рядки

Як щодо вашого імені? Наберіть ваше ім'я в лапках, як тут:

    >>> "Ola"
    'Ola'

Щойно ви створили свій перший рядок! Це послідовність символів, що може бути оброблена комп'ютером. Рядок має постійно починатися і закінчуватися одним і тим же символом. Це може бути одинарна (`'`) або подвійна (`"`) лапка (немає ніякої різниці)! Лапки вказують Python, що всередині них рядок.

Рядки можна об'єднувати. Спробуйте:

    >>> "Hi there " + "Ola"
    'Hi there Ola'

Також можна множити рядки на число:

    >>> "Ola" * 3
    'OlaOlaOla'

Якщо вам раптом треба поставити апостроф всередині рядка, то існує два шляхи це зробити.

Використавши подвійні лапки:

    >>> "Runnin' down the hill"
    "Runnin' down the hill"

або ж екранувати апостроф за допомогою оберненої косої риски (англ. backslash `\`):

    >>> 'Runnin\' down the hill'
    "Runnin' down the hill"

Гарно, еге ж? Щоб побачити своє ім'я, написане великими літерами, наберіть:

    >>> "Ola".upper()
    'OLA'

Ви щойно застосували до свого рядка `upper` __функцію__! Функція (така як `upper()`) - це набір інструкцій, які повинен виконувати Python над заданим об'єктом (`"Ola"`) з моменту її виклику.

Якщо ви раптом забажаєте дізнатися про число літер, що містяться у вашому імені, то для цього також існує функція!

    >>> len("Ola")
    3

Здивовані, чому іноді ви викликаєте функції із `.` наприкінці рядка (на зразок `"Ola".upper()`), а іноді ви спочатку викликаєте функцію і вказуєте рядок у дужках? Що ж, в деяких випадках, функції належать об'єктам, як `upper()`, котра може бути виконана лише над рядком. У цьому випадку, ми називаємо функцію __методом__. Іншого разу, функції не належать до жодного об'єкту і можуть використовуватись стосовно різних типів об'єктів, як `len()`. Саме тому ви використовуємо `"Ola"` у якості параметра для функції `len`.

### Підсумок

Гаразд, досить стосовно рядків. Отже, ви вже ознайомилися із такими поняттями як:

- __командний рядок__ - набір команд (коду) в командному рядку Python дає результат у відповідях на Python
- __числа і рядки__ - в Python числа використовуються для математичних розрахунків, а рядки - для текстових об'єктів
- __оператори__ - на зразок + та \*, комбінують значення і продукують нове
- __функції__ - на зразок upper() та len(), виконують дії над об'єктами.

Це є основи кожної мови програмування, яку ви вивчатимете. Готові приступити до чогось складнішого? Б'ємось об заклад, що так!

## Помилки

Спробуємо щось нове. Чи можемо ми отримати довжину числа тим же методом, як ми це робили для нашого імені? Наберіть `len(304023)` та натисніть `Enter`:

    >>> len(304023)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: object of type 'int' has no len()

Ми отримали нашу першу помилку! Вона говорить про те, що об'єкт типу "int" (integers, цілі числа) не має довжини. І що ж нам тепер робити? Можливо, можна записати наше число у формі рядка? Рядки ж мають довжину, правда?

    >>> len(str(304023))
    6

Спрацювало! Ми використали функцію `str` всередині функції `len`. `str()` перетворює будь-що на рядки.

- Функція `str` перетворює речі на __рядки__
- Функція `int` перетворює речі на __цілі числа__

> Важливо: ми можемо перетворювати числа на текст, однак, не можемо перетворити текст на числа - чому б дорівнювало `int('hello')`?

## Змінні

Важливою концепцію в програмуванні є змінні. Змінна - це ніщо більше, ніж ім'я для чогось, що можна буде використовувати пізніше. Програмісти використовують ці змінні для збереження даних, щоб зробити свій код більш читабельним і, таким чином, їм не потрібно пам'ятати зайве.

Скажімо, ми хочемо створити змінну і назвати її `name`:

    >>> name = "Ola"

Бачите? Це просто! Просто: name дорівнює Ola.

Як ви зауважили, ваша програма не повернула нічого як вона це робила до того. Отже, як ми впевнимось, що змінна насправді існує? Просто введіть `name` і натисніть `enter`:

    >>> name
    'Ola'

Урра! Ваша перша змінна :)! Ви завжди можете змінити значення, на яке вона посилатиметься:

    >>> name = "Sonja"
    >>> name
    'Sonja'

Також можна використовувати її у функціях:

    >>> len(name)
    5

Файно, хіба ні? Звісно, змінні можуть представляти будь-що, числа також! Спробуйте:

    >>> a = 4
    >>> b = 6
    >>> a * b
    24

А якщо ми використали неправильне ім'я? Чи можете ви передбачити, що станеться? Спробуймо!

    >>> city = "Tokyo"
    >>> ctiy
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    NameError: name 'ctiy' is not defined

Помилка! Як бачите, Python має різні типи помилок і дана помилка називається **NameError**. Python виведе для вас цю помилку, якщо ви спробуєте використати досі не визначену змінну. Якщо ж ви зіткнетеся із цією помилкою пізніше, перевірте свій код, чи не зробили ви помилки в написанні імен змінних.

Поекспериментуйте із цим усім і подивіться, що можна робити!


## Функція print

Спробуйте наступне:

    >>> name = 'Maria'
    >>> name
    'Maria'
    >>> print(name)
    Maria

Коли ви просто набираєте `name`, Python інтерпретує відповіді за допомогою рядкового *представлення* змінної 'name', котра є набором літер M-a-r-i-a, взятим в одинарні лапки, ''. Коли ви повідомляєте `print(name)`, Python "надрукує" значення змінної на екран, без лапок, що є більш акуратним.

Як ми потім побачимо, `print()` є також корисним коли ми хочемо надрукувати речі з внутрішніх функцій, або ж коли хочемо надрукувати речі в декілька рядків.


## Списки

Окрім рядків та чисел, Python має усі види різних типів об'єктів. Наразі ми збираємося представити вашій увазі один із них, що називається __список__. Списки є саме тим, про що ви й подумали: це об'єкти, що є списками інших об'єктів :)

Створимо список:

    >>> []
    []

Так, цей список пустий. Не дуже корисно, чи не так? Створимо список лотерейних чисел. Ми не бажаємо увесь час повторюватись, тож покладемо усе до змінної:

    >>> lottery = [3, 42, 12, 19, 30, 59]

Гаразд, маємо список! Що ми можемо із цим робити? Давайте глянемо скільки лотерейних номерів міститься у списку. Не маєте жодного уявлення, яку функцію для цього можна використати? Ви вже це знаєте!

    >>> len(lottery)
    6

Так! `len()` може дати вам кількість об'єктів у списку. Зручно, правда ж? Може, тепер здійснимо сортування:

    >>> lottery.sort()

Ця функція нічого не повертає, вона лише змінює порядок, в якому з'являються числа у списку. Давайте надрукуємо список знову і подивимось, що ж трапилося:

    >>> print(lottery)
    [3, 12, 19, 30, 42, 59]

Як бачимо, числа у вашому списку тепер відсортовано починаючи з найменшого і закінчуючи найбільшим значенням. Вітаємо!

Можливо, ми хочемо відсортувати числа у зворотньому порядку? Давайте це зробимо!

    >>> lottery.reverse()
    >>> print(lottery)
    [59, 42, 30, 19, 12, 3]

Просто, чи не так? Якщо ви забажаєте щось додати до свого списку, то можете це зробити за допомогою наступної команди:

    >>> lottery.append(199)
    >>> print(lottery)
    [59, 42, 30, 19, 12, 3, 199]

Якщо захочете показати лише перше число, то можете зробити це використавши __індекси__. Індекс - це номер, що повідомляє про те, звідки у списку взято елемент. Програмісти вважають за краще рахувати з 0, таким чином, перший об'єкт у списку має індекс 0, наступний - 1 і так далі. Спробуйте наступне:

    >>> print(lottery[0])
    59
    >>> print(lottery[1])
    42

Як бачимо, ви можете отримати доступ до різних об'єктів списку використавши ім'я списку та індекс об'єкта всередині квадратних дужок.

Для того, щоб видалити що-небудь із списку, вам потрібно використовувати вище вивчені __індекси__ і команду `pop()`. Давайте спробуємо на прикладі та нагадаємо, що ми вивчили раніше; ми будемо видаляти перший елемент з нашого списку.

    >>> print(lottery)
    [59, 42, 30, 19, 12, 3, 199]
    >>> print(lottery[0])
    59
    >>> lottery.pop(0)
    >>> print(lottery)
    [42, 30, 19, 12, 3, 199]

Працює чудово!

Для додаткового задоволення, спробуйте деякі індекси: 6, 7, 1000, -1, -6 або -1000. Подивіться, чи здатні ви передбачити результат команди перед її застосуванням. Чи мають ці результати якийсь смисл?

Список усіх доступних методів для списку міститься у цьому розділі документації з Python: https://docs.python.org/3/tutorial/datastructures.html

## Словники

Словник є чимось подібним до списку, але доступ до значень отримується шляхом пошуку за ключем замість індексу. Ключ може являти собою будь-який рядок або число. Синтаксис для визначення пустого словника:

    >>> {}
    {}

Це показує, що ви просто створили пустий словник. Урра!

А тепер спробуйте набрати наступну команду (спробуйте також замінити на вашу власну інформацію):

```python
>>> participant = {'name': 'Ola', 'country': 'Poland', 'favorite_numbers': [7, 42, 92]}
```

За допомогою вказаної команди ви щойно створили змінну із назвою `participant` і трьома парами ключ-значення:

- ключ `name` вказує на значення `'Ola'` (об'єкт `string` - рядок),
- `country` вказує на `'Poland'` (інший об'єкт `string` - рядок),
- і `favorite_numbers` вказує на `[7, 42, 92]` (об'єкт `list` - список з трьома числами всередині).

Можна перевірити значення індивідуальних ключів, використовуючи наступний синтаксис:

    >>> print(participant['name'])
    Ola

Бачите, усе подібно до списку. Але вам не треба пам'ятати індекс - лише ім'я.

Що трапиться, якщо запитати Python про значення ключа, якого не існує? Не здогадуєтесь? Давайте спробуємо і подивимось!

    >>> participant['age']
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    KeyError: 'age'

Погляньте, інша помилка! Цього разу - **KeyError**. Python допомагає і підказує вам про те, що ключа `'age'` не існує в даному словнику.

Коли ж варто використовувати словник, а коли список? Що ж, гарне питання. Просто вирішимо його подумки перед тим, як подивитися відповідь у наступному рядку.

- Вам необхідна лише впорядкована послідовність елементів? Користуйтеся списком.
- Вам потрібні значення асоційовані із ключами, так що ви можете ефективно переглядати їх (за допомогою ключа) пізніше? Користуйтеся словником.

Словники, як і списки, є *змінюваними*, це означає, що вони можуть бути змінені після створення. Ви можете додати нові пари ключ/значення до словника після того, як він був створений, наприклад:

    >>> participant['favorite_language'] = 'Python'

Як і для списків, використання методу `len()` для словників, повертає значення пар ключ-значення в словнику. Наберіть команду:

    >>> len(participant)
    4

Сподіваюся, це наразі має сенс. :) Готові до ще більшого задоволення від роботи зі словниками? Перейдіть на наступний рядок, щоб побачити дещо дивовижне.

Можна використовувати команду `pop()` для видалення елементів зі словника. Скажімо, якщо ви бажаєте видалити значення, що відповідає ключу `'favorite_numbers'`, просто наберіть наступну команду:

    >>> participant.pop('favorite_numbers')
    >>> participant
    {'country': 'Poland', 'favorite_language': 'Python', 'name': 'Ola'}

Як бачимо з результатів, пару ключ-значення, що відповідає ключу 'favorite_numbers' було видалено.

Аналогічно можна змінювати значення, асоційоване з уже існуючим ключем зі словника. Наберіть:

    >>> participant['country'] = 'Germany'
    >>> participant
    {'country': 'Germany', 'favorite_language': 'Python', 'name': 'Ola'}

Як бачимо, значення ключа `'country'` було змінено із `'Poland'` на `'Germany'`. :) Вражаюче? Ура! Ви щойно освоїли іншу дивовижну річ.

### Підсумок

Чудово! Тепер ви знаєте багато про програмування. У цій останній частині ви дізналися про такі поняття, як:

- __помилки__ - тепер ви знаєте як читати та розуміти помилки, що з'являються якщо Python не розуміє отриманої команди
- __змінні__ - імена для об'єктів, що дозволяють вам спростити процес написання коду і робить його більш читабельним
- __списки__ - списки певним чином впорядкованих об'єктів
- __словники__ - об'єкти, що зберігають пари ключ-значення

Не дочекаєтеся переходу до наступної частини? :)

## Порівняння

Велика частина програмування включає речі, пов'язані із порівнянням. Що є найпростішою річчю для порівняння? Звісно, числа. Давайте подивимось як це працює:

    >>> 5 > 2
    True
    >>> 3 < 1
    False
    >>> 5 > 2 * 2
    True
    >>> 1 == 1
    True
    >>> 5 != 2
    True

Ми надали Python деякі числа для порівняння. Як бачимо, Python вміє порівнювати не лише числа, а й результати операцій. Гарно, еге ж?

Цікаво, чому ми використали два однакові знаки `==`, щоб порівняти на рівність числа? Ми використовуємо `=` для присвоєння значень змінним. Завжди, __завжди__ треба писати `==`, якщо ви бажаєте здійснити перевірку двох чисел на рівність одне одному. Ми також можемо перевіряти, чи два об'єкти є нерівними. Для цього ми використовуємо символ `!=`, як показано в прикладі вище.

Задайте для Python ще дві задачі:

    >>> 6 >= 12 / 2
    True
    >>> 3 <= 2
    False

щодо `>` та `<` - усе просто, але що означають `>=` і `<=`? Читайте їх як:

- x `>` y означає x більше ніж y
- x `<` y означає x менше ніж y
- x `<=` y означає x менше або дорівнює y
- x `>=` y означає x більше або дорівнює y

Чудово! Хочете ще? Спробуйте це:

    >>> 6 > 2 and 2 < 3
    True
    >>> 3 > 2 and 2 < 1
    False
    >>> 3 > 2 or 2 < 1
    True

Ви можете задавати для Python стільки чисел для порівння скільки заманеться, і він дасть вам результат! Дуже розумно, чи не так?

- __and__ - якщо ви використовуєте оператор `and`, обидва порівнюваних значення мають бути істинними - True для того, щоб і уся команда була істинною - True
- __or__ - якщо ви використовуєте оператор `or`, лише одне із порівнюваних значень мають бути істинними - True для того, щоб і уся команда була істинною - True

Чи чули ви про вираз "порівняння яблук і апельсинів"? Давайте спробуємо Python еквівалент:

    >>> 1 > 'django'
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: '>' not supported between instances of 'int' and 'str'

Бачимо тут, що як і у виразі, Python не в змозі порівняти число (`int`) та рядок (`str`).
Натомість, виводиться **TypeError** і повідомляє нас про те, що ці два типи не можна порівнювати між собою.

## Логічні типи

Між іншим, ви щойно дізналися про новий типу об'єкту в Python. Він називається логічним - __Boolean__ - і, можливо, це найпростіший тип.

Існує лише два логічних об'єкти:
- Істинне: True
- Хибне: False

Але для того, щоб Python міг це зрозуміти, треба завжди писати 'True' (перша літера - велика, а решта - маленькі). __true, TRUE, tRUE не працюють - лише True є правильним.__ (Те ж саме стосується і 'False' також.)

Логічні значення також можуть бути змінними! Погляньте:

    >>> a = True
    >>> a
    True

Можна також зробити теж саме по-іншому:

    >>> a = 2 > 5
    >>> a
    False

Практикуйте із логічними типами спробувавши запустити наступні команди:

- `True and True`
- `False and True`
- `True or 1 == 1`
- `1 != 2`

Вітання! Логічними типи - одна із найкрутіших властивостей програмування, і ви щойно освоїли, як їх застосовувати!

# Збережіть!

Досі ми писали увесь наш Python код в інтерпретаторі, що обмежує нас написанням лише одного рядка за раз. Зазвичай програми зберігаються у файлах і виконуються __інтерпретатором__ або __компілятором__ нашої мови програмування. Досі ми запускали наші програми одним рядком в Python __інтерпретаторі__. Для наступних задач нам знадобиться більше, ніж один рядок коду, отже, нам потрібно:

- Закрити Python інтепретатор
- Відкрити наш вибраний текстовий редактор
- Зберегти певний код в python файлі
- Запустити його!

Щоб вийти з Python інтерпретатора, яким ми користувалися до цього, просто наберіть функцію ```exit()```:

    >>> exit()
    $

Ви повернетеся назад до командного рядка.

Раніше ми вже обрали для себе редактор коду в розділі [редактор коду](../code_editor/README.md). А тепер ми маємо відкрити цей редактор і написати якийсь код в новому файлі:

```python
print('Hello, Django girls!')
```

Очевидно, ви тепер є досить досвідченим Python програмістом, отже, можете написати у ваш код усе, що ви до цього часу вивчили.

А тепер треба зберегти файл і дати йому описове ім'я. Назвімо файл **python_intro.py** і збережемо його на вашому робочому столі. Ви можете називати файл як завгодно, тільки важливо, щоб назва закінчувалась на __.py__. Закінчення __.py__ говорить нашій операційній системі, що це **виконуваний файл Python** і Python може його запускати.

> **Примітка** Ви повинні помітити одну з найкрутіших фіч редакторів коду: кольори! У консолі Python все було одного кольору, тепер ви повинні побачити, що функція `print` має інший колір, ніж рядок, який вона друкує. Це називається "підсвіткою синтаксису", і це справді корисна функція для програміста. Різний колір слів дає вам підказку щодо правильності набору тексту чи орфографічної помилки (згодом зверніть увагу на колір слова `def` в тілі функції). Це одна з вагомих причин, чому ми використовуємо редактор коду :)


По тому, як файл успішно збережено, час запустити його! Використовуючи навики отримані під час освоєння розділу, що стосувався командного рядка, скористайтеся терміналом, щоб **змінити директорію** на робочий стіл.

Для Mac, команда буде виглядати так:

    $ cd ~/Desktop

Для Linux, вона буде на зразок (слово "Desktop" може бути перекладене вашою мовою):

    $ cd ~/Desktop

І для Windows, це буде так:

    > cd %HomePath%\Desktop

Якщо ви застрягли, просто попросіть допомоги.

Використовуйте Python, щоб виконати код у файлі, таким чином:

    $ python3 python_intro.py
    Hello, Django girls!

Гаразд! Ви щойно запустили вашу першу Python програму, яка була збережена у файлі. Чудові відчуття?

Тепер ви можете переходити до важливого інструменту у програмуванні:

## If...elif...else

Багато речей в програмі мають бути виконані лише тоді, коли виконуються задані умови. Саме тому Python має інструмент, що називається __умовою if - якщо__.

Замініть код вашого файлу **python_intro.py** на наступне:

```python
if 3 > 2:
```

Якщо ми збережемо зміни і запустимо цей файл, то побачимо наступну помилку:

    $ python3 python_intro.py
    File "python_intro.py", line 2
             ^
    SyntaxError: unexpected EOF while parsing

Python очікує від нас подальших інструкцій, які повинні бути виконані, якщо умова `3 > 2` виявляється істинною (тобто `True`). Спробуємо змусити Python надрукувати “It works!”. Змініть код у файлі **python_intro.py** на наступне:

```python
if 3 > 2:
    print('It works!')
```

Зауважили, яким чином ми зробили відступ в 4 пробіли для наступного рядка коду? Це необхідно робити для того, щоб Python знав, який шматок коду запускати, якщо результати умови істинні. Можна зробити відступ і в один пробіл, але майже усі Python програмісти роблять відступ у 4 пробіли, щоб було акуратніше. Один `tab` також рахується як 4 пробіли.

Збережіть і запустіть знову:

    $ python3 python_intro.py
    It works!

### Що ж, якщо ні?

У попередніх прикладах код виконувався лише, коли умови були істинними - True. Однак, Python також має умови `elif` та `else`:

```python
if 5 > 2:
    print('5 is indeed greater than 2')
else:
    print('5 is not greater than 2')
```

Коли запустимо це, буде виведено:

    $ python3 python_intro.py
    5 is indeed greater than 2

Якщо 2 було числом більшим за 5, то далі буде виконуватися друга команда. Просто, правда ж? Подивимося як працює `elif`:

```python
name = 'Sonja'
if name == 'Ola':
    print('Hey Ola!')
elif name == 'Sonja':
    print('Hey Sonja!')
else:
    print('Hey anonymous!')
```

і в результаті:

    $ python3 python_intro.py
    Hey Sonja!

Бачите, що тут відбуваеться? `Elif` вказує додаткові умови для перевірки, якщо результат попередніх умов є невдалим.

Ви можете додати стільки виразів `elif`, скільки вам до вподоби одразу після виразу `if`. Наприклад:

```python
volume = 57
if volume < 20:
    print("It's kinda quiet.")
elif 20 <= volume < 40:
    print("It's nice for background music")
elif 40 <= volume < 60:
    print("Perfect, I can hear all the details")
elif 60 <= volume < 80:
    print("Nice for parties")
elif 80 <= volume < 100:
    print("A bit loud!")
else:
    print("My ears are hurting! :(")
```

Python послідовно виконує всі перевірки та друкує:

    $ python3 python_intro.py
    Perfect, I can hear all the details

### Підсумок

В останніх трьох вправах ви освоїли такі поняття, як:

- __порівняння__ - в Python можна порівнювати елементи використовуючи `>`, `>=`, `==`, `<=`, `<` та оператори `and`, `or`
- __Логічний тип - Boolean__ - тип об'єкту, що може дорівнювати лише одному з двох значень: `True`- Істинне або `False` - Хибне
- __Збереження файлів__ - зберігання коду в файлах дозволяє виконувати більші програми.
- __if...elif...else__ - умови, що дозволяють виконувати код лише коли виконуються певні умови.

Час для останньої частини цього параграфу!

## Ваші власні функції!

Пам'ятаєте функції на зразок `len()`, що можна виконувати в Python? Що ж, гарні новини - зараз ви дізнаєтесь, як писати свої власні функції!

Функція - це набір інструкцій, які Python повинен виконати. Кожна функція в Python починається із ключового слова `def`, отримує ім'я і може містити певні параметри. Почнемо з простого. Перепишемо код в **python_intro.py** наступним чином:

```python
def hi():
    print('Hi there!')
    print('How are you?')

hi()
```

Окей, наша перша функція готова!

Ви можете запитати, для чого ми написали ім'я функції наприкінці файлу. Це тому, що Python зчитує файл і виконує його згори донизу. Отже, для того, щоб скористатися нашою функцією, ми повинні написати її знову унизу.

А тепер запустимо і подивимось, що станеться:

    $ python3 python_intro.py
    Hi there!
    How are you?

Це було просто! Побудуємо нашу першу функцію з параметрами. Скористаємося попереднім прикладом - функцією, що говорить 'hi' особі, що її запускає - з іменем:

```python
def hi(name):
```

Як бачимо, зараз ми задали для нашої функції параметр, який назвали `name`:

```python
def hi(name):
    if name == 'Ola':
        print('Hi Ola!')
    elif name == 'Sonja':
        print('Hi Sonja!')
    else:
        print('Hi anonymous!')

hi()
```

Пам'ятайте: функція `print` відділена відступами від команди `if` на чотири пробіли. Це тому, що функція запускається, коли виконується умова. Давайте подивимося, як це відбувається зараз:

    $ python3 python_intro.py
    Traceback (most recent call last):
    File "python_intro.py", line 10, in <module>
      hi()
    TypeError: hi() missing 1 required positional argument: 'name'

Ой, помилка. На щастя, Python надає нам дуже корисне повідомлення про помилку.
Воно повідомляє нас про те, що функція `hi()` (та, яку ми визначили) має один необхідний аргумент (`name`) і що ми забули передати його, коли здійснювали виклик функції.
Виправимо це наприкінці файлу:

```python
hi("Ola")
```

І запустимо знову:

    $ python3 python_intro.py
    Hi Ola!

А якщо ми змінимо ім'я?

```python
hi("Sonja")
```

Запустимо:

    $ python3 python_intro.py
    Hi Sonja!

А тепер що ви думаєте про те, що станеться, якщо ми вкажемо тут інше ім'я? (Не Ola і не Sonja) Спробуємо і подивимося, чи ви маєте рацію. Маємо отримати на виході:

    Hi anonymous!

Чудово, чи не так? Таким чином вам не потрібно повторюватись кожного разу, коли ви захочете змінити ім'я особи, з якою має вітатися наша функція. І саме тому нам потрібні функції - ви ж бо ніколи не хочете повторювати свій код!

Виконаємо дещо складніші маніпуляції - існує безліч імен, набагато більше, ніж лише два, і написати умови для кожного з них буде досить складно, правда ж?

```python
def hi(name):
    print('Hi ' + name + '!')

hi("Rachel")
```

А тепер виконаємо програму:

    $ python3 python_intro.py
    Hi Rachel!

Вітаємо! Ви щойно розібралися з тим, як писати функції :)

## Цикли

Це вже остання частина. Усе було швидко, чи не так? :)

Програмісти не люблять повторюватись. Програмування - це процес автоматизації всього, тому ми не хочемо вітати кожну людину по імені вручну, правильно? Тут пригодяться цикли.

Ще пам'ятаєте про списки? Давайте створимо список дівчат:

```python
girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
```

Ми б хотіли привітатися із кожною з них персонально. Щоб це зробити, у нас є функція `hi`, отже, використаємо її в циклі:

```python
for name in girls:
```

Вираз ```for``` поводиться подібно до виразу ```if```, а код, наведений нижче повинен мати відступи в чотири пробіли.

Тут наведено повну версію коду у файлі:

```python
def hi(name):
    print('Hi ' + name + '!')

girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
for name in girls:
    hi(name)
    print('Next girl')
```

А коли ми запустимо усе це:

    $ python3 python_intro.py
    Hi Rachel!
    Next girl
    Hi Monica!
    Next girl
    Hi Phoebe!
    Next girl
    Hi Ola!
    Next girl
    Hi You!
    Next girl

Як бачимо, все, що міститься всередині виразу `for` із відступом буде повторюватися для кожного елементу зі списку `girls`.

Також можна використовувати `for` для чисел, використовуючи функцію `range`:

    for i in range(1, 6):
        print(i)

Що виведе на екран:

    1
    2
    3
    4
    5

`range` - це функція, що створює список чисел, що йдуть одне за одним ці числа задаються вами як параметри).

Зауважте, що друге з цих двох чисел, не входить до списку, що виводиться на екран Python (тобто `range(1, 6)` рахує від 1 до 5, але не включає число 6). Це тому, що "діапазон" є напіввідкритим, і під цим ми розуміємо, що він включає перше значення, але не останнє.

## Підсумок

Ось і все. __Ви молодці!__ Це був складнуватий розділ, тому ви можете пишатися собою. Ми ж безумовно пишаємося вами, адже ви вже багато чого досягли!

Ви можете зробити коротку перерву - можливо потрібний відпочинок для ваших очей, розминка, невелика прогулянка, перш ніж перейдете до наступного розділу. :)

![Cupcake](images/cupcake.png)