# Traffic Matrix 
Репозиторий для проекта по курсу "Численные методы оптимизации" в МФТИ. 

Лектор: Гасников А.В.

Семинарист: Меркулов Д.М.

[🎓 Сайт Меркулова Д.М. с материалами курса](https://fmin.xyz/)


## Идея
[📘 Proposal проекта](https://github.com/GrebenkovaO/Traffic_matrix/blob/master/Proposal_Grebenkova.pdf)

Проект заключается в исследовании способов оценки матрицы транспорта(корреспонденций) в условии невозможности её прямого измерения с помощью линейного программирования и рандомных нейронных сетей. 
За основу взяты две статьи:
- [Traffic matrix estimation: existing techniques and new directions](https://www.researchgate.net/publication/221164004_Traffic_matrix_estimation_existing_techniques_and_new_directions),
- [On the use of random neural networks for traffic matrix estimation in large-scale IP networks](https://www.researchgate.net/publication/220762265_On_the_use_of_random_neural_networks_for_traffic_matrix_estimation_in_large-scale_IP_networks).

В рамках курса стояла задача повторить результаты статей и сравнить их.

## Ресурсы 
В процессе работы над проектом возник вопрос поиска открытых датасетов с матрицами корреспонеденций. Ниже представлены все найденные мной источники.
Стоит отметить, что в каждом их них матрицы и графы представлены в разных форматах, поэтому для каждого конкретного алгоритма нужна своя предобработка.
- [Transportation Networks](https://github.com/bstabler/TransportationNetworks/),
- [Файл с московскими данными, любезно предоставленный Екатериной Котляровой](https://github.com/tamamolis/traffic_flows/blob/master/traffic_moscow.csv)
- [Проект Totem](https://totem.info.ucl.ac.be/dataset.html)
- [2004 Abilene data](http://www.maths.adelaide.edu.au/matthew.roughan/project/traffic_matrix/)
- [Генератор графов](https://github.com/GrebenkovaO/Traffic_matrix/blob/master/code/RNN.ipynb)

#### Про работу с каждым датасетом
- [Обработчик для первых двух источников (Автор: Котлярова Екатерина)](https://github.com/tamamolis/TransportNet/blob/master/Stable%20Dynamic%20%26%20Beckman/data_handler.py)
- В проекте Totem есть специальный обработчик-программа. Пробовать совмещать со своим кодом не пробовала.
- Для датасета Abilene есть написанный обработчик на Perl.
- Параметры генератора описаны в коде

🚨 Обратите внимание! Не каждый датасет подходит под все задачи и все алгоритмы. Иногда нужный параметр можно получить из данных, однако не всегда это возможно.
К примеру, в подходе с рандомной нейронной сетью нужно было иметь большое количество временных замеров потока по каждому ребру и так же подробное описание графа, для построения кратчайшего пути.

## [Random neural network](https://en.wikipedia.org/wiki/Random_neural_network)
[💻 Единственная реализованная версия для Python.](https://pypi.org/project/rnnsim/)

[📒 Пример использования в проекте](https://github.com/GrebenkovaO/Traffic_matrix/blob/master/code/RNN.ipynb)

⚠️ Версия не очень удобна для сравнения качества модели, так как Accuracy выдается строчкой и нет хорошей документации для изменения кода. Стоит либо использовать,
дорабатывая нужные вам куски, или писать сеть заново.

## Линейное программирование
Существует большое количество различных библиотек для решения задач линейного программирования. Я использовала PULP в своем [коде.](https://github.com/GrebenkovaO/Traffic_matrix/blob/master/code/LP.ipynb)

## Результаты работы
Все полученные результаты и краткое описание проекта доступны по [ссылке.](https://github.com/GrebenkovaO/Traffic_matrix/blob/master/Poster.pdf)


