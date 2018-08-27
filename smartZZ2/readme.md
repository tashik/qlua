Индикатор Зиг-Заг, построенный по классическому алгоритму.

Индикатор также позволяет видеть уровни вершин, выводит точки середины волны, также есть некий алгоритм предсказания движения
(вывод целевых зон). Также есть вывод метки с статистикой по последним 5-и волнам, точкам формации XABCD.

<a href="http://funkyimg.com/view/2KKiR" target="_blank"><img src="http://funkyimg.com/i/2KKiR.png" alt="Free Image Hosting at FunkyIMG.com" border="0"></a>

Основные настройки

	showCalculatedLevels = 0, -- показывать уровни от прошлого движения
	showextraCalculatedLevels = 0, -- показывать расширения уровней от прошлого движения
	regimeOfCalculatedLevels = 2, -- 1- последнее движение, 2 - последний максимальный диапазон
	deepZZForCalculatedLevels = 10, -- глубина поиска последнего максимального диапазона по вершинам. До 20.
	showZZLevels = 0, -- показывать уровни от вершин
	numberOfZZLevels = 10, -- сколько показывать уровней от вершин до 20
	numberOfHistoryZZLevels = 0, -- сколько показывать уровней от вершин для истоических данных
	showCoG = 1, -- показывать центр движения для вил Эндрюса
	numberOfShownCOG = 3, --  глубина показа COG
	showTargetZone = 1, -- показывать целевую зону
	numberOfMovesForTargetZone = 5, --  глубина поиска движений для предсказания
	spreadOfTargetZone = 10, -- диапазон целевой зоны (%)
	showLabel = 1, -- показывать метку паттерна
	showFiboExt = 1, -- показывать расширение фибо волны
	LabelShift = 100, -- сдвиг метки от вершины

Чтобы выводилась метка по паттернам надо задать идентификтор графика.

Целевая зона строится по двум прицпам. Если удалось определить паттерн движения по этим соотношениям
(алгоритм взял из индикатора MT5).

-- Алгоритм: проверка размера волн и корректировка по следующим от- |
-- ношениям "Идеальных пропорций" ("Золотое сечение" версия 1):     |
-- (в терминах XABCD точки равны: A = X, B = A, C = B, D = B, E = D)|
--   №    (D-E)/(D-C)   "ЗС версия1" №  (E-D)/(C-D)   "ЗС версия1"  |
--   M1    2             1.618       W1  0.3334        0.3819       |
--   M2    0.5           0.5         W2  0.6667        0.618        |
--   M3    1.5           1.2720      W3  1.5           1.2720       |
--   M4    0.6667	 0.618       W4  0.5           0.5          |
--   M5    1.3334        1.2720      W5  2             1.618        |
--   M6    0.75          0.618       W6  0.25          0.25         |
--   M7    3             3.0000      W7  0.5           0.5          |
--   M8    0.3334        0.3819      W8  2             1.618        |
--   M9    2             1.618       W9  0.3334        0.3819       |
--   M10   0.5           0.5         W10 3             3.0000       |
--   M11   0.25          0.25        W11 0.75          0.618        |
--   M12   2             1.618       W12 1.3334        1.2720       |
--   M13   0.5           0.5         W13 0.6667        0.618        |
--   M14   1.5           1.2720      W14 1.5           1.2720       |
--   M15   0.6667        0.618       W15 0.5           0.5          |
--   M16   0.3334        0.3819      W16 2             1.618        |


Если паттерн не определен, то целевая зона определяется через усреднение (numberOfMovesForTargetZone = 5) прошлых движений.



