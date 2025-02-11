# Forward Education Waste Management with Smart Garbage Bins - Modify Tutorial

```package
fwd-edu-breakout=github:ssande-fwd/fwd-ext-testing/fwd-breakout
sonar=github:ssande-fwd/fwd-ext-testing
```

```template
input.onButtonPressed(Button.A, function () {
    lidClosed = false
})
input.onButtonPressed(Button.AB, function () {
    binFull = false
    timeFull = 0
})
input.onButtonPressed(Button.B, function () {
    lidClosed = true
})
let lidClosed = false
let binFull = false
let timeFull = 0
timeFull = 0
binFull = false
basic.forever(function () {
    if (lidClosed) {
        fwdMotors.leftServo.fwdSetAngleAndWait(0)
        if (fwdSensors.sonar1.fwdDistancePastThreshold(0.1, fwdSensors.ThresholdDirection.Under)) {
            binFull = true
        } else {
            binFull = false
        }
    } else {
        fwdMotors.leftServo.fwdSetAngleAndWait(90)
    }
    basic.pause(100)
})
basic.forever(function () {
    if (binFull) {
        basic.pause(1000)
        timeFull += 1
        if (timeFull >= 10) {
            fwdSensors.ledRing.fwdSetAllPixelsColour(0xff0000)
        } else {
            fwdSensors.ledRing.fwdSetAllPixelsColour(0x00ff00)
        }
    }
    basic.pause(100)
})
```

## Activity 1: Build Your Project @showdialog
Let's build a smart garbage bin prototype to optimize waste management routes! We are going to do this in four parts:  
1. **Build** our automated smart home
2. **Add code** to bring our project to life  
3. **Modify** our project to learn about other sensors  
4. Apply what we learned with a small **challenge**

## Activity 2: Code Your Project @showdialog
We need to connect our project to the computer to make it come to life with code!

The code will be the instructions that tell our micro:bits what to do.

## Code Step 1 @showdialog
IMPORTANT! Make sure your Climate Action Kit Breakout Board is turned on and your micro:bit is plugged into your computer.

<img src="https://raw.githubusercontent.com/climate-action-kits/pxt-fwd-edu/main/tutorial-assets/pluganim.webp" alt="Plug micro:bit into USB port on computer" style="display: block; width: 60%; margin:auto;">

## Code Step 2 @showdialog
Click the three dots beside the ``|Download|`` button, then click on _Connect Device_.
Next, follow the steps to pair your micro:bit.

<img src="https://raw.githubusercontent.com/climate-action-kits/pxt-fwd-edu/main/tutorial-assets/pairmicrobitGIF.webp"  alt="Pairing gif" style="display: block; width: 60%; margin:auto;">

## Code Step 3
Click the ``|Download|`` button to download the starter code to your project on the micro:bit in your project.

## Activity 3: Modify Your Project @showdialog
We have a smart garbage bin prototype that opens and closes, and measures how full the bin is. Let's explore how to optimize our project by **modifying** our code!

As you go through the next steps:

* Use the instructions at the top of the screen to **modify** your code.  
* When you are ready for more information, click **'Tell Me More!'**  
* If you need help with the code, click the **lightbulb**!