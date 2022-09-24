# HW4_SOLID

### Описание/Пошаговая инструкция выполнения домашнего задания:
На примере реализации игры «Угадай число» продемонстрировать практическое применение SOLID принципов.
Программа рандомно генерирует число, пользователь должен угадать это число. При каждом вводе числа программа пишет больше или меньше отгадываемого. Кол-во попыток отгадывания и диапазон чисел должен задаваться из настроек.
В отчёте написать, что именно сделано по каждому принципу.
Приложить ссылку на проект и написать, сколько времени ушло на выполнение задачи.


### Отчет по домашнему заданию
S - Принцип единственной ответственности. Классы `NumberGenerator`, `Level`, `UserLevelInit`, `GameDescription`, `BaseGame`, `MultilevelGame` выполняют свою одну единственную задачу и только "одну" причину для изменения.   
O - Принцип открытости/закрытости. Класс `UserGame` наследует класс `BaseGame` и расширяет его функционал не измененяя базовый.   
L - Принцип подстановки Лисков. Вместо базового класса `BaseGame` можно подставить его производный класс `MultilevelGame` и программа будет корректно выполнена.    
I - Принцип разделения интерфейсов. Интерфейс `IUserGame` разделен на интерфейсы `IGameInit`, `IGamePlay`. Это позволяет классу `BaseGame` реализовывать `IGamePlay`, а классу `UserGame` реализовывать оба этих интерфейса. Т.о. данное разделение интерфейсов при их реализации позволяет зависеть только от тех методов, которые необходимы и будут использоваться.  
D - Принцип инверсии зависимостей. Класс `Level` не зависит от конретной реализации `ConsoleLevelManager`, а зависит от абстракции `ILevelManager`. Это позволяет создавать разные реализации менеджера игры. А также писать менее связный код, который легче модифицировать и обновлять.   
