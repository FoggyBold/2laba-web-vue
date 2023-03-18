# ProgressBar
ProgressBar

## Содержание
- [Параметры](#Параметры)
- [Переменные](#Переменные)
- [Computed](#Computed)
- [Methods](#Methods)
- [Использование](#Использование)
- [Примеры](#Примеры)
- [Команда проекта](#команда-проекта)

## Параметры
startValue - начальное значение для progress bar, тип - Number, деволтное значение - 0

## Переменные
percentage - текущее значение, на котором все завязано

## Computed
percent - форматирует число из percentage, используя метод toFixed
color - формирцует цвет на основе percentage

## methods
percentage - текущее значение, на котором все завязано
decrease - уменьшает число процентов на 10 при нажатии на кнопку "-10"
increase - увеличивется число процентов на 10 при нажатии на кнопку "+10"

## Использование
<ProgressBar :startValue="..что-то.."/>

## Использование
Одиночная прогресс линия
![image](https://github.com/FoggyBold/2laba-web-vue/blob/main/tests/single.gif)