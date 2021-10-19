# Датчики: Акселерометр

```package
core
radio
microphone
```

```template
basic.forever(function () {
	
})
```

```blocks
basic.forever(function () {
	
})
```
## Step 0 @showDialog
Привет! Сегодня мы научимся измерять движение и положение Micro:bit в пространстве.
## Step 1
### Акселерометр
Акселерометр - это датчик движения, который измеряет ускорение Micro:bit. 
Больше об этом датчике в [видео](https://youtu.be/UT35ODxvmS0).
## Step 2 @showHint
### Акселерометр
Все блоки работы с датчиками находятся во вкладке ``||input.ввод||``. Чтобы обнаруживать движение, добавим блок ``||input.жесты||`` в нашу программу.
Этот блок той же формы, что и блок ``||basic.постоянно||``, и он тоже запускает программу.
```hint
Этот блок выглядит так:
```
```blocks
input.onGesture(Gesture.Shake, function () {
	
})
```
## Step 3 @showHint
### Игральная кость
Блок ``||input.жесты||`` позволяет запустить программу с помощью одного из 11 жестов. Давай превратим Micro:bit в игральную кость! Напишем программу, которая будет показывать случайное число при встряхивании.

```blocks
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(randint(1, 6))
})
```
## Step 4 @showDialog
### Что за жесты?
Как ты уже знаешь, жест `встряхивание` запускает программу, если устройство встряхивают.
-  Жесты `экран вверх`, `экран вниз`, `логотип вверх`, `логотип вниз`, `наклон влево` и `наклон вправо` запускаются, если Micro:bit занимает выбранное положение в пространстве.
- `свободное падение` происходит, если устройство падает.
- `3g`, `6g` and `8g` означает уровень перегрузок. Эти жесты запускаются, если перемещать устройство достаточно быстро.


## Step 5 @showHint
### Поворот лица
Мы можем использовать сразу несколько жестов, чтобы выполнять разные команды. Давай напишем программу, которая будет переворачивать лицо, если Micro:bit перевернут вверх ногами. Загрузи программу в Micro:bit и проверь! 
```blocks
input.onGesture(Gesture.LogoUp, function () {
    basic.showLeds(`
        . . . . .
        . # . # .
        . . . . .
        # . . . #
        . # # # .
        `)
})
input.onGesture(Gesture.LogoDown, function () {
    basic.showLeds(`
        . # # # .
        # . . . #
        . . . . .
        . # . # .
        . . . . .
        `)
})
```

## Step 6
### Теперь твой черёд!
Время выполнить задание! С помощью блока ``||input.жесты||``, напиши программу, которая покажет на экране стрелку в направлении земли вне зависимости от поворота устройства.
```hint
Указатель земли в действии:
```
![](https://raw.githubusercontent.com/CraftAndCode/mood-badge/master/earthpointer.gif)


## Step 7 @showDialog
### Ответы: Указатель земли
```blocks
input.onGesture(Gesture.LogoUp, function () {
    basic.showArrow(ArrowNames.South)
})
input.onGesture(Gesture.TiltLeft, function () {
    basic.showArrow(ArrowNames.West)
})
input.onGesture(Gesture.TiltRight, function () {
    basic.showArrow(ArrowNames.East)
})
input.onGesture(Gesture.LogoDown, function () {
    basic.showArrow(ArrowNames.North)
})
```
## Step 8
Поздравляем, урок завершён! Теперь ты знаешь, какие блоки измеряют положение Micro:bit в пространстве и его ускорение! 