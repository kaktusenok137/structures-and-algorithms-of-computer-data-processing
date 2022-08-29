# Выполнение

<p>Для нахождения некоторого элемента (ключа) в заданном <b>неупорядоченном массиве</b> используется <i>алгоритм линейного (последовательного) поиска</i>. 
  Он работает как с неотсортированными массивами, так и отсортированными, но для вторых существуют алгоритмы эффективнее линейного поиска.</p>
<p>Слово «последовательный» содержит в себе основную идею метода. Начиная с первого, все элементы массива последовательно просматриваются и сравниваются с искомым. 
  Если на каком-то шаге текущий элемент окажется равным искомому, тогда элемент считается найденным, и в качестве результата возвращается номер этого элемента, 
  либо другая информация о нем. (Далее, в качестве выходных данных будет выступать номер элемента). Иначе, следуют возвратить что-то, что может оповестить о его 
  отсутствии в пройденной последовательности.</p>
<p>Вторым методом является <i>быстрый линейный поиск</i> - проверка на окончание массива осуществляется лишь при совпадении очередного элемента с искомым. 
  Если этот элемент находится внутри массива, то поиск заканчивается удачно и элемент считается найденным. Если же этот элемент оказался (N + 1)-ым, 
  то искомого элемента в массиве нет.</p>
<p>Для нахождения некоторого элемента (ключа) в заданном <b>упорядоченном массиве</b> используется <i>быстрый линейный поиск</i>. Применяя алгоритм быстрого линейного 
  поиска для поиска элемента в упорядоченном массиве, поиск можно прекратить, если очередной элемент массива будет больше искомого. Это будет означать, 
  что искомого элемента в массиве нет. В случае поиска элемента, который есть в массиве, этот алгоритм аналогичен алгоритму быстрого линейного поиска в 
  неупорядоченном массиве.</p>
<p>Вторым алгоритмом является <i>бинарный поиск</i>. Главный шаг при бинарном поиске — взять элемент из середины массива и, если он не равен искомому, то в зависимости 
  от его значения ту или другую половину массива убрать из рассмотрения.</p>
  
<p>Алгоритм бинарного поиска:</p>
1. Определить середину массива.
2. Если элемент, находящийся в середине массива, совпадает с искомым, поиск завершен.
3. Если элемент из середины массива больше искомого, применить бинарный поиск к первой половине массива.
4. Если элемент из середины массива меньше искомого, бинарный поиск необходимо применить ко второй половине массива.
5. Пункт 1-4 повторять, пока размер области поиска не уменьшается до нуля. Если это произойдет — ключа в массиве нет.
	
<p>Третий алгоритм поиска в упорядоченном массиве – <i>блочный поиск</i>.  Суть его в том, что массив, упорядоченный по возрастанию, разбивается на определенное число блоков.</p> В процессе поиска искомый элемент последовательно сравнивается с последним элементом блоков. Если искомый элемент меньше последнего элемента очередного блока, то искомый элемент может находиться только внутри этого блока. Для поиска элемента в блоке можно применить линейный поиск.


<p align="center">Таблица 4.1 Максимальное количество операций сравнения</p>

![image](https://user-images.githubusercontent.com/76211121/187227892-4ec52c72-fc1a-409e-9564-71b339278001.png)

![image](https://user-images.githubusercontent.com/76211121/187227928-a051e480-ffeb-4e63-b798-4b9b689ca3cb.png)
<p align="center">Рисунок 1. Диаграмма зависимости максимального количества операций сравнения от количества элементов в массиве</p>

Для экспериментального определения среднего числа сравнений необходимо найти суммарное число сравнений при поиске всех элементов массива и разделить на количество элементов.

<p align="center">Таблица 4.2 Среднее количество операций сравнения</p>

![image](https://user-images.githubusercontent.com/76211121/187228122-8bdb563c-cd12-42f2-8da6-dd6926775d1e.png)

![image](https://user-images.githubusercontent.com/76211121/187228177-6eff0308-d279-4f5d-8e87-60888747b98f.png)
<p align="center">Рисунок 2. Диаграмма зависимости среднего количества операций сравнения от количества элементов в массиве</p>

# Выводы

<p>Худшим оказался алгоритм линейного поиска, так как в  лучшем случае, когда искомый элемент занимает первую позицию, алгоритм произведет всего одно сравнение,
  а в худшем N, где N — количество элементов в массиве. Худшему случаю соответствуют две ситуации: искомый элемент занимает последнюю позицию, 
  или он вовсе отсутствует в массиве.</p>
<p>Алгоритм линейного поиска не часто используется на практике, поскольку принцип работы «в лоб» делает скорость решения им задачи очень низкой. Его применение
  оправдано на небольших и/или неотсортированных последовательностях, но когда последовательность состоит из большого числа элементов, и с ней предстоит работать
  не раз, тогда наиболее оптимальным решением оказывается предварительная сортировка этой последовательности с последующим применением двоичного или другого, 
  отличного от линейного, алгоритма поиска.</p>
<br><p>Лучшие результаты на поиске элемента в массиве показал алгоритм бинарного поиска, что позволяет считать данный алгоритм самым стойким.</p>
<br><b>Линейный поиск:</b> сложность алгоритма 2*n, среднее количество операций сравнения n+1.
<br><b>Быстрый линейный поиск:</b> сложность алгоритма n+1, среднее количество операций сравнения (n+1)/2.
<br><b>Бинарный поиск:</b> порядок функции алгоритма бинарного поиска равен log2n.
<br><b>Блочный поиск:</b> сложность алгоритма 2*√n, среднее количество операций сравнения √n.