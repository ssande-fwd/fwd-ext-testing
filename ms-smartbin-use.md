# Forward Education Waste Management with Smart Garbage Bins - Use Tutorial

```package
fwd-edu-breakout=github:ssande-fwd/fwd-ext-testing/fwd-breakout
sonar=github:ssande-fwd/fwd-ext-testing
```

```template
input.onButtonPressed(Button.A, function () {
    lidClosed = true
})
input.onButtonPressed(Button.B, function () {
    lidClosed = false
})
let fillLevel = 0
let lidClosed = false
lidClosed = true
fwdMotors.rightServo.fwdSetAngle(0)
basic.forever(function () {
    led.plotBarGraph(
    fillLevel,
    100
    )
    if (fwdSensors.sonar1.fwdDistancePastThreshold(0.02, fwdSensors.ThresholdDirection.Under)) {
        fwdSensors.ledRing.fwdSetAllPixelsColour(0xff0000)
        fillLevel = 75
    } else if (fwdSensors.sonar1.fwdDistancePastThreshold(0.04, fwdSensors.ThresholdDirection.Under)) {
        fwdSensors.ledRing.fwdSetAllPixelsColour(0xff8000)
        fillLevel = 50
    } else if (fwdSensors.sonar1.fwdDistancePastThreshold(0.06, fwdSensors.ThresholdDirection.Under)) {
        fwdSensors.ledRing.fwdSetAllPixelsColour(0xffff00)
        fillLevel = 25
    } else {
        fwdSensors.ledRing.fwdSetAllPixelsColour(0x00ff00)
        fillLevel = 0
    }
    if (lidClosed == true) {
        fwdMotors.rightServo.fwdSetAngle(0)
    }
    if (lidClosed == false) {
        fwdMotors.rightServo.fwdSetAngle(60)
    }
})
```

## Activity 1: Build Your Project @showdialog
Let's build a smart garbage bin prototype to optimize waste management routes! We are going to do this in three parts: 
1. **Build** our automated smart bin prototype
2. **Add code** to bring our project to life  
3. **Use** your project to understand how they works

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

## Activity 3: Use Your Project @showdialog
Now that we've built our automated smart garbage bin prototype, we'll start by **using** the sample code to see how it works.

As you go through the next steps:

* **Use** the instructions at the top of the screen.  
* When you are ready for more information, click **'Tell Me More!'**  
* If you need help with the code, click the **lightbulb!**