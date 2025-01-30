# Аннотация
Задача 1

Исходными данными являются параметры описанные ниже:

de = 20.4e-2; % расстояние между ушами
c = 340.29; % скорость звука м/с
ds = 2; % расстояние до источника в метрах
rs = 0.1; % радиальная скорость в м/с
fd = 44100; % частота дискретизации (сэмплирования) в Гц
t = 10; % длительность звука в секундах
fs = 500; % частота звука в Гц 

Далее для высчитываются углы прихода сигнала и для каждого угла высчитывается ITD.
Затем круг (по которому "летает" источник) делится на сектора и в каждом секторе к сигналу прибавляется своя задержка. Это делается сначала для одного канала. На выходе получается массив сигнала с задержками для одного канала, далее этот массив инвертируется для другого канала. В итоге получается двумерный массив с информацией о сигнале для правого и левого канала. В конце используется функция Matlab для записи массива в аудиофайл формата wav.

Задача 2 

Исходные данные представлены ниже:

fs = 44100; % Частота дискретизации
t = 10; % Длительность в секундах
num_samples = round(t * fs); % Общее количество сэмплов
out_signal = zeros(num_samples, 1); % выходной сигнал

У пользователя запрашивается частота и коэйициент затухания. Затем генерируется сигнал на заданной частоте и приводится к необходимому виду для работы алгоритма.
Далее используется уравнение описывающее алгоритм Карплуса-Стронга

𝑦(𝑛) = 𝑥(𝑛) + 𝛼𝑦(𝑛 − 𝑀),

где 𝑥(𝑛) – входной сигнал; 𝑀 – задержка; α – коэффициент затухания. 
В конце используется функция Matlab для записи массива в аудиофайл формата wav.

Задача 3

Исходными данными являются координаты постов РТМ и измеренные разности времени прихода сигналов  между постами i,j.
Расстояния от ИРИ до постов можно выразить через координаты постов:
d1 = sqrt((x - x1)^2 + (y - y1)^2);
d2 = sqrt((x - x2)^2 + (y - y2)^2);
d3 = sqrt((x - x3)^2 + (y - y3)^2); 
где х и у координаты ИРИ, х1 у1, х2 у2, х3 у3 координаты постов
Следовательно задержки между постами можно выразить:
d1 - d2 = dd12;
d1 - d3 = dd13;
где dd12 и dd13, разность хода между первым и вторым, первым и третим постами соответсвенно 
Далее следует решение системы уравнениий относительно х и у.
В результате получаем значения х и у для ИРИ и выводится график для наглядного представления.
