# Wildfire Tracking with Autonomous Vehicles - Extension
```package
=github:ssande-fwd/fwd-ext-testing/fwd-breakout
=github:ssande-fwd/fwd-ext-testing
```
## 
* This is the complete code for this activity.
```template
input.onButtonPressed(Button.A, function () {
    IsDrivingEnabled = true
})
input.onButtonPressed(Button.AB, function () {
    basic.showNumber(input.temperature() + 273)
    basic.showString("K")
    basic.showNumber(input.temperature() * (9 / 5) + 32)
    basic.showString("F")
})
input.onButtonPressed(Button.B, function () {
    IsDrivingEnabled = false
})
let IsDrivingEnabled = false
fwdMotors.setupDriving(
fwdMotors.leftServo,
fwdMotors.rightServo
)
let lightThreshold = 100
let temperatureThreshold = 25
basic.forever(function () {
    if (IsDrivingEnabled) {
        for (let index = 0; index < 4; index++) {
            fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 50)
            basic.pause(5000)
            fwdMotors.turn(25)
            if (input.lightLevel() > lightThreshold || input.temperature() > temperatureThreshold) {
                for (let index = 0; index < 4; index++) {
                    music.playTone(262, music.beat(BeatFraction.Double))
                    music.playTone(262, music.beat(BeatFraction.Whole))
                }
            } else {
                music.stopAllSounds()
            }
            basic.pause(1000)
        }
    } else {
        fwdMotors.stop()
    }
})
```
