# Введение
В этом документа будет описан план тестирования разрабатываемого приложения. Более подробнуб информацию о приложении можно найти в документе README.md. 
Тестировщику необоходимо иметь браузер на тестируемом пк. 
Цель тестирования: проверить работоспобоность приложения. 

# Объекты тестирования
В разрабатываемом приложении четыре экрана:

- "All";
- "Новости";
- "Today";
- "Next 7 days";
- "Overdue";
- "Done";
- "Forgotten";
Каждый экран имеет свои потоки событий. В соответствии с ними могут быть разработаны различные сценарии использования.

Атрибуты качества платформы по ISO 25010:

1. функциональность 
- функциональная полнота: приложение должно выполнять все заявленные функции
- функциональная корректность: приложение должно выполнять все заявленные функции корректно
2. производительность
- временная характеристика: приложение должно загружать данные не более 5 секунд
3. удобство использования
- эстетика пользовательского интерфейса: элементы переключения между экранами должны быть всегда доступны пользователю

Данные атрибуты были взяты с учётом специфики приложения.

# Риски

Данные приложения хранятся в локальном хранилище браузера пользователя. Его размер составляет 5 Мб - чего должно быть предостаточно. Но если выйти за границы выделенной памяти, то будет сообщено о соответсвующей ошибке. После чего придеться поудалять некоторые задачи, для освобождения памяти.

# Аспекты тестирования
## Добавление задачи
Этот вариант использования необходимо протестировать на: 
1. Добавление задачи;
2. Соответствие описания задачи введенной информации;
3. Добавление пустой задачи;

## Корректная работа с локальным хранилищем
Этот вариант использования необходимо протестировать на:
1. Сохранение введенных задач после перезагрузки браузера; 
2. Корректное сохранение всех полей введенных задач;

## Просмотр задач по категориям
Этот вариант использования необходимо протестировать на:
1. Добавление задачи в соответсвующую категорию;

## Поиск задач по ключевым словам
Этот вариант использования необходимо протестировать на:
1. Корретный вывод задач по заданной информации;

## Удаление задачи
Этот вариант использования необходимо протестировать на:
1. Удаление задачи из всех категорий задач;

## Отметка задачи как выполненной
Этот вариант использования необходимо протестировать на:
1. Пропадание задачи из всех категорий, где находятся активные задачи, при нажатии на чекбокс возле задачи;
2. Появление отмеченной задачи в списке выполненных;

## Подходы к тестированию
Для тестирования приложения необходимо вручную проверить каждый вариант использования.

# Представление результатов

## Сценарий 001-1: добавление задачи
1. запустить приложение;
2. в открывшемся окне в форму описания задачи ввести описание задачи;
3. нажать на кнопку "Add Task";
<br>Ожидаемый результат: на экране появилась задача с введенным описанием.
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 001-2: добавление пустой задачи
1. запустить приложение; 
2. нажать на кнопку "Add Task";
<br>Ожидаемый результат: список задач отображаемых на главном экране не должен измениться.
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 001-3: соответсвие описания задачи введенной информации
1. запустить приложение; 
2. в открывшемся окне в форму описания задачи ввести описание задачи;
3. рядом с формой описания задачи установить дедлайн задачи;
3. нажать на кнопку "Add Task";
<br>Ожидаемый результат: задача должна добавиться в соответсвующую категорию исходя от ее даты дедлайна. 
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 002-1: Сохранение введенных задач после перезагрузки браузера
1. запомнить задачи отображаемые приложением;
2. перезагрузить страницу браузера(F5), либо закрыть страницу и открыть приложение заново;
3. проверить совпадение задач, с задачами отображаемыми в п.1;
<br>Ожидаемый результат: список задач после перезагрузки не изменится.
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 002-2: Корректное сохранение всех полей введенных задач
1. запомнить задачи отображаемые приложением по категориям;
2. перезагрузить страницу браузера(F5), либо закрыть страницу и открыть приложение заново;
3. проверить совпадение задач, с задачами отображаемыми в п.1 по категориям;
<br>Ожидаемый результат: список задач по категориям после перезагрузки не изменится.
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 003-1: Просмотр задач по категориям
1. добавить задачу с сегодняшней датой дедлайна;
<br>Ожидаемый результат: появление введенной задачи в списке задач "Today".
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 003-2: Просмотр задач по категориям
1. добавить задачу без даты дедлайна;
<br>Ожидаемый результат: появление введенной задачи тольков списке задач "All".
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 003-3: Просмотр задач по категориям
1. добавить задачу с просроченной датой дедлайна(меньше 7 дней);
<br>Ожидаемый результат: появление введенной задачи в списке задач "Overdue".
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 003-4: Просмотр задач по категориям
1. добавить задачу с просроченной датой дедлайна(больше 7 дней);
<br>Ожидаемый результат: появление введенной задачи в списке задач "Forgotten".
<br>Фактический результат:
<br>Оценка:

## Сценарий 003-5: Просмотр задач по категориям
1. добавить задачу с датой дедлайна, которая будет в ближайшие 7 дней;
<br>Ожидаемый результат: появление введенной задачи в списке задач "Next 7 days".
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 003-6: Просмотр задач по категориям
1. добавить задачу;
2. нажать на чекбокс возле введенной задачи
<br>Ожидаемый результат: появление введенной задачи в списке задач "Done".
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 004-1: Поиск задач по ключевым словам
1. ввести интересующую информацию в соответвующее поле окна;
2. нажать на кнопку "Search";
<br>Ожидаемый результат: появление задач описание которых соответсвует введенной информации.
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 005-1: Удаление задачи
1. нажать на кнопку "Delete" возле соответсвующей задачи;
<br>Ожидаемый результат: удаление задачи из всех категорий задач.
<br>*Фактический результат:*
<br>*Оценка:*

## Сценарий 006-1: Отметка задачи как выполненной
1. нажать на чекбокс возле интересующей задачи;
<br>Ожидаемый результат: удаление задачи из всех категорий задач и ее добавление в категорию "Done".
<br>*Фактический результат:*
<br>*Оценка:*

# Выводы
Данный план теста даёт нам возможность проверить полный функционал приложения. И после положительного прохождения всех тестов - можно утверждать о корректной работе приложения.