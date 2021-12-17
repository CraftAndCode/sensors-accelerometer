# Sensors: accelerometer

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
Hello! Today we'll learn how to measure movement with the Micro:bit.
## Step 1
### Accelerometer
An accelerometer is a motion sensor that can tell you the acceleration or movement of the Micro:bit. 
To learn more, watch [this video](https://youtu.be/UT35ODxvmS0).
## Step 2 @showHint
### Accelerometer
All the code blocks for sensors are located inside the ``||input.input||`` category of your toolbox. To detect movement, we can add an ``||input.on gesture||`` block to our code.
As you can see, this block is the same shape as the ``||basic.forever||`` block, so it is also used to launch a program.
```hint
It looks like this:
```
```blocks
input.onGesture(Gesture.Shake, function () {
    
})
```
## Step 3 @showHint
### Let's make a dice cube!
The ``||input.on gesture||`` block allows you to choose one of 11 gestures to start your program. We'll turn the Micro:bit into a dice cube that shows a random number when shaken. Assemble the code as shown and try shaking your Micro:bit!

```blocks
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(randint(1, 6))
})
```
## Step 4 @showDialog
### What are the gestures?
As you already know, the `shake` gesture happens when you shake the device.
- `screen up`, `screen down`, `logo up`, `logo down`, `tilt left` and `tilt right` refer to the different orientations of the Micro:bit.
- `free fall` happens when your device is being dropped.
- `3g`, `6g` and `8g` are the levels of acceleration. These gestures occur when you move the device fast enough.

## Step 5 @showHint
### A rotating face
You can add different programs to start on different gestures. Let's make a face that turns upside down when we turn the Micro:bit upside down. Download the code to your Micro:bit and try flipping it! 
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
### Now it's your turn!
Here's a challenge for you! Use the ``||input.on gesture||`` block to make an earth pointer that displays an arrow that points towards the ground no matter the orientation of the Micro:bit.
```hint
The earth pointer in action:
```
![](https://raw.githubusercontent.com/CraftAndCode/mood-badge/master/earthpointer.gif)

## Step 7 @showDialog
### Answers: Earth pointer
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
Congratulations, this lesson is complete! Now you know how to track the motion and orientation of the Micro:bit! 

