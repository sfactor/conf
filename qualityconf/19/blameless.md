# Blameless environment: никто не должен писать качественный код

Никита Соболев, wemake.services

## Бывает, что всё очень плохо

* Плохой код, никто не думает о качестве кода.
* Плохие процессы, аутсорс и бардак.
* Плохие клиенты и вообще всё плохо.

Наверное, это люди виноваты!
А вот когда люди изменятся, всё станет иначе.
Ещё наверное, в других местах работают другие люди, и те люди лучше, и там работать лучше.

Но нет, это неправда.

Хочется это поменять, создать новый порядок.
Совершенно непонятно, как его создать.
В книжках не написано и в университете не учили.

## Постановка задачи

Начнём с постановки задачи.
Бывают задачи из одной строки.
Человек делает такую задачу и у него получается не то.
Проще обвинить человека, но на самом деле задача плохо поставлена.

Хорошие постановки задач:

* Короткие и понятные.
* Упорядоченные: ясно, в каком порядке их лучше делать.
* Индивидуальные: кому-то принадлежат.

Если постановка хорошая, то люди, внезапно, делают хорошо.

## Чего на самом деле хочет заказчик

Есть требования: что должно быть сделано в целом.
Но по требованиям нельзя работать.
Нужна декомпозиция задач в документации.

Требования — что нужно сделать, документация — как.
Из требований можно генерировать документацию.
Следующий шаг — сделать тесты, а потом написать код.

Получается, чтобы заказчик и разработчик встретились, нужно выстроить цепочку от требований к коду.

## Общение

Люди хотят общаться, и на работе это может быть проблемой.
Например, они разговаривают и вырывают друг друга из состояния потока.
А ещё есть митинги, на которых люди тратят время друг друга.

Люди конфликтны.
Особенно, когда они находятся в тесном помещении и ситуация сталкивает их.

Бывает также, что люди пропадают, особенно если они работали удалённо.
Просто больше не отвечают на звонки.

Как структурировать общение?

1.  Удалить соцсети.
    Тогда люди не могут тебе написать куда угодно.
    
2.  Выбрать один канал для общения, который удобен для работы.
    В wemake.services для общения выбрали GitLab.
    Всё там, даже вопрос по работе задают там.
    Обсудить новую технологию? Создай тикет.
    Обсудить Игру Престолов? Нет, спасибо, с этим к друзьям.

## Все пишут плохой код

Мы созданы не для того, чтобы писать код.
Код вообще сложный.
Нормально, что нам сложно писать код.
Все пишут плохой код.

Чтобы облегчить написание кода, нужна **строгость**.
Строгость нам даст CI.
Он должен быть **неотвратимым** и обязательным для всех.
Если кто-то может коммитить в мастер, будет бардак.

Всё это вместе ведёт к **развитию**.
Если есть строгий CI, каждый кусочек кода делает проект лучше.
Но люди всё равно будут делать ошибки и это нормально.

Можно возвращать ошибки людям, вместе с обвинениями.
«Ты сделал плохой код, иди и поправь».
Но это плохо работает.

## Blameless environment

Если в проекте есть баг, чья это проблема?
Это проблема проекта и больше ничья.
Баг нужно исправить так, чтобы он больше не случился.

* Если он в коде, написать регрессионный тест.
* Если в инфраструктуре — использовать инструмент, который его предотвратит.

Когда исправляешь баги на системном уровне, появляется развитие.

Следующий шаг после CI — ревью кода.
И каждый шаг имеет смысл, только если правильно выполнен предыдущий.
Если код не прошёл CI, незачем его ревьюить.
Если задача неправильно поставлена, то никакой CI этого не обнаружит, и ревью тоже не всегда.

## Баги — это хорошо

Бывает культура, в которой баги — это плохо.
А если человек не тестировщик и зарепортил баг — он плохой, срывает процесс и суёт палки в колёса.
Зарепортить баг — это как будто сказать «код твой плохой и ты сам плохой».

В blameless environment баги — это благо.
Баги помогают развиваться.
Поэтому нужно поощрять и уважать людей, которые репортят баги.
Как этого добиться?

## Виноваты не люди, виновата система

система, которая поощряет:

* писать плохой код,
* тратить время на встречи,
* и делать всё остальное, что плохо.

Исправляйте систему.

## Имплементация

Вот принципы работы в wemake.services:

*   Полная свобода действий.
    Хочешь — работаешь.
    Не хочешь — не работаешь.
*   Нет общения.
    В том числе нет системы информирования о том, будет человек сегодня работать или нет.
*   Поэтому нет команды.
*   Боты управляют людьми.
*   Всё код: код, тесты, требования, документация.
*   Оплата за результат, тикеты и ревью.
*   Всё проверяется: тикеты, ревью, код.
