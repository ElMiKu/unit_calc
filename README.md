**Тестовое задание**
Напишите на PHP функцию поиска самого дешевого маршрута.
Функция должна получать на входе три параметра:
название населенного пункта отправления,
название населенного пункта прибытия,
а также список, каждый элемент которого представляет собой названия неких двух населенных пунктов и стоимость проезда от одного населенного пункта до другого.

На выходе функция должна возвращать самый дешевый маршрут между населенными пунктами отправления и прибытия,
в виде списка транзитных населенных пунктов (в порядке следования),
а также общую стоимость проезда.

Пожалуйста, обратите внимание на то, что нас интересует не только правильность реализации алгоритма, но и общее качество кода.
Код должен быть пригоден для включения в состав программного продукта. !


________________


**Решение**

Для решение задачи используется алгоритм "Дейкстры".

Алгоритм можно заменить, установив его через метод TransportCalculator::setAlgorithm,
например на алгоритм  "Флойда-Уоршалла" или др.



**Использование**

Примеры выполнения в файлах: test.php и test2.php

<pre>
$calc = new TransportCalculator($routes);
$calc->calc('Москва','Краснодар');

echo "маршрут:";
var_dump($calc->getPath());

echo "\n Стоимость проезда: ".$calc->getCost();
</pre>

$routes  - коллекция маршрутов со стоимостью, например:

<pre>
$routes = [
    ['from'=>'Москва','to'=>'Самара','cost'=>2],
    ['from'=>'Москва','to'=>'Воронеж','cost'=>3],
    ...
    ];
</pre>


**Тесты**

   UnitTests - на данный момент отутствуют.
   
**Roadmap**
   
 - Рефакторинг
 - unit-тестирование
 - реализация других алгоритмов
 - тестирование на больших объемах данных
 
   
   


