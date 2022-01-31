# Парадигмы программирования у2020
##### Решения домашних заданий курса "Парадигмы программирования"
## 1. [Бинарный поиск](https://github.com/ptyvvs/itmo-paradigms/blob/main/java-solutions/search/BinarySearchMissing.java)
##### Условия
Реализуйте итеративный и рекурсивный варианты бинарного поиска в массиве.
На вход подается целое число x и массив целых чисел a, отсортированный по невозрастанию. Требуется найти минимальное значение индекса i, при котором a[i] <= x.
Для функций бинарного поиска и вспомогательных функций должны быть указаны, пред- и постусловия. Для реализаций методов должны быть приведены доказательства соблюдения контрактов в терминах троек Хоара.
##### Интерфейс программы
Первый аргумент командной строки — число x.<br/>
Последующие аргументы командной строки — элементы массива a.<br/>
Пример запуска: `java BinarySearch 3 5 4 3 2 1`. Ожидаемый результат: `2`.<br/>
##### Модификация
Если в массиве a отсутствует элемент, равный x, то требуется вывести индекс вставки в формате, определенном в `Arrays.binarySearch`.<br/>
Класс должен иметь имя `BinarySearchMissing`
## 2. [Очередь на массиве](https://github.com/ptyvvs/itmo-paradigms/tree/main/java-solutions/queue)
##### Условия
Определите модель и найдите инвариант структуры данных «очередь». Определите функции, которые необходимы для реализации очереди. Найдите их пред- и постусловия, при условии что очередь не содержит null.<br/>
Реализуйте классы, представляющие циклическую очередь с применением массива.<br/>
Класс `ArrayQueueModule` должен реализовывать один экземпляр очереди с использованием переменных класса.<br/>
Класс `ArrayQueueADT` должен реализовывать очередь в виде абстрактного типа данных (с явной передачей ссылки на экземпляр очереди).<br/>
Класс `ArrayQueue` должен реализовывать очередь в виде класса (с неявной передачей ссылки на экземпляр очереди).<br/>
Должны быть реализованы следующие функции (процедуры) / методы:

- `enqueue` – добавить элемент в очередь;
- `element` – первый элемент в очереди;
- `dequeue` – удалить и вернуть первый элемент в очереди;
- `size` – текущий размер очереди;
- `isEmpty` – является ли очередь пустой;
- `clear` – удалить все элементы из очереди.

Инвариант, пред- и постусловия записываются в исходном коде в виде комментариев.
Обратите внимание на инкапсуляцию данных и кода во всех трех реализациях.
Напишите тесты к реализованным классам.
##### Модификация
Реализовать метод `toArray`, возвращающий массив, содержащий элементы, лежащие в очереди в порядке от головы к хвосту.
Исходная очередь должна остаться неизменной
Дублирования кода быть не должно
## 3. [Очередь на связном списке](https://github.com/ptyvvs/itmo-paradigms/tree/main/java-solutions/queue)
##### Условия
Определите интерфейс очереди Queue и опишите его контракт.<br/>
Реализуйте класс `LinkedQueue` — очередь на связном списке.<br/>
Выделите общие части классов `LinkedQueue` и `ArrayQueue` в базовый класс AbstractQueue.<br/>
##### Модификация
Добавить в интерфейс очереди и реализовать метод `toArray`, возвращающий массив, содержащий элементы, лежащие в очереди в порядке от головы к хвосту.
## 4. [Функциональные выражения на JavaScript](https://github.com/ptyvvs/itmo-paradigms/blob/main/javascript-solutions/functionalExpression.js)
##### Условия
Разработайте функции `cnst`, `variable`, `add`, `subtract`, `multiply`, `divide`, `negate` для вычисления выражений с одной переменной.
Функции должны позволять производить вычисления вида:<br/>
`let expr = subtract(
    multiply(
        cnst(2),
        variable("x")
    ),
    cnst(3)
);`
`println(expr(5));`          
При вычислении такого выражения вместо каждой переменной подставляется значение, переданное в качестве параметра функции expr (на данном этапе имена переменных игнорируются). Таким образом, результатом вычисления приведенного примера должно стать число 7.<br/>
Тестовая программа должна вычислять выражение x2−2x+1, для x от 0 до 10.<br/>
При выполнение задания следует обратить внимание на:
- Применение функций высшего порядка.
- Выделение общего кода для операций.
##### Модификация
Дополнительно реализовать поддержку переменных `y`, `z`
## 5. [Объектные выражения на JavaScript](https://github.com/ptyvvs/itmo-paradigms/blob/main/javascript-solutions/objectExpression.js)
##### Условия
Разработайте классы `Const`, `Variable`, `Add`, `Subtract`, `Multiply`, `Divide`, `Negate` для представления выражений с одной переменной.<br/>
Пример описания выражения 2x-3:<br/>
`let expr = new Subtract(
    new Multiply(
        new Const(2),
        new Variable("x")
    ),
    new Const(3)
);`

`println(expr.evaluate(5));`
                    
При вычислении такого выражения вместо каждой переменной подставляется её значение, переданное в качестве аргумента метода evaluate. Таким образом, результатом вычисления приведенного примера должно стать число 7.<br/>
Метод `toString()` должен выдавать запись выражения в обратной польской записи. Например, `expr.toString()` должен выдавать `"2 x * 3 -"`
##### Модификация
Дополнительно реализовать поддержку функций:
- `ArcTan (atan)` – арктангенс, `1256 atan` примерно равно `1.57`;
- `ArcTan2 (atan2)` – арктангенс, `841 540 atan2` примерно равно `1`;
## 6. Обработка ошибок на JavaScript
##### Условия
Добавьте в предыдущее домашнее задание функцию `parsePrefix(string)`, разбирающую выражения, задаваемые записью вида `(- (* 2 x) 3)`. Если разбираемое выражение некорректно, метод `parsePrefix` должен бросать человеко-читаемое сообщение об ошибке.<br/>
Добавьте в предыдущее домашнее задание метод `prefix()`, выдающий выражение в формате, ожидаемом функцией `parsePrefix`.
##### Модификация
Дополнительно реализовать поддержку унарных операций:
- `Sinh (sinh)` – гиперболический синус, `(sinh 3)` немного больше `10`;
- `Cosh (cosh)` – гиперболический косинус, `(cosh 3)` немного меньше `10`;





