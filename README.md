# pxt-powerfunctions - Power Functions IR Sender

Control your LEGO® Power Functions motors using your micro:bit, an infrared LED and MakeCode.
This package turns your micro:bit into a remote control for your Power Functions devices.

## MakeCode Blocks Example

![alt text](https://github.com/philipphenkel/pxt-powerfunctions/raw/master/code_example.png "MakeCode Blocks Example")

## MakeCode JavaScript Example

```javascript
basic.showIcon(IconNames.Heart)
powerfunctions.useIrLedPin(AnalogPin.P0)
powerfunctions.setMotorDirection(PowerFunctionsMotor.Blue1, PowerFunctionsDirection.Backward)

input.onButtonPressed(Button.A, () => {
    powerfunctions.moveForward(PowerFunctionsMotor.Blue1)
})

input.onButtonPressed(Button.B, () => {
    powerfunctions.float(PowerFunctionsMotor.Blue1)
})

basic.forever(() => {
    led.plotBarGraph(
    input.lightLevel(),
    255
    )
    if (input.lightLevel() > 200) {
        powerfunctions.float(PowerFunctionsMotor.Blue1)
        basic.pause(5000)
        powerfunctions.setSpeed(PowerFunctionsMotor.Blue1, 2)
        basic.pause(3000)
    }
})
```

## Disclaimer

LEGO® is a trademark of the LEGO Group of companies which does not sponsor, authorize or endorse this project.

## License

Copyright (C) 2017 Philipp Henkel

Licensed under the MIT License (MIT). See LICENSE file for more details.

## Supported targets

* for PXT/microbit
* for PXT/calliope

