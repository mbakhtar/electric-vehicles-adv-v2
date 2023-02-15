# Electric Vehicle Tutorial 
```package
cakEnergy=github:climate-action-kits/pxt-climate-action-kit-energy
```
## @showhint
Add ``||cakLandServos:turn servo at P1 to degrees 35||`` block from the ``||cakLandServos:Servo||`` drawer
```blocks
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
```
## @showhint
Now add ``||cakLandServos:turn right motor + pin on||``
```blocks
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
```
## @showhint
Set the speed of the driving motor by adding ``||cakLandMotor:turn right motor at speed 0||``
change the speed from 0 to 50
```blocks
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
```
## @showhint
Now add the following blocks under the ``||basic:forever||`` loop. 
Add ``||cakLandSonar:graph proximity max range 0 cm||``. Change the range number from 0 to 50
```blocks
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    cakLandSonar.graphSonar(50)
})
```
## @showhint
In the ``||basic:forever||`` loop add a delay by nesting a ``||basic:pause||``
block before the ``||cakLandSonar:graph proximity max range 50 cm||``.
Change the ``||basic:pause||`` value to 1 sec or 1000 ms.
```blocks
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
})
```
## @showhint
Now nest an ``||logic:If true then||`` block after the 
``||cakLandSonar:graph proximity max range 50 cm||``
```blocks
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
    if(true){
    }
})
```
## @showhint
Replace the ``||logic:true||`` condition with ``||cakLandsonar:sonar is closer than 0 cm||`` block
```blocks
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
    if(cakLandSonar.isSonar(cakLandSonar.Comparison.Closer,30)){
    }
})
```
## @showhint
When the sonar's condition is true the ``||cakLandMotor:motor||`` should stop. 
Add ``||cakLandMotor:stop motors||`` block and 
nest it under ``||logic:if then||``
```blocks
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
        if(cakLandSonar.isSonar(cakLandSonar.Comparison.Closer,30)){
        cakLandMotor.stop()
    }
})
```
## @showhint
Add a ``||basic:pause||`` of 1 sec or 1000ms after the ``||cakLandMotor:stop motors||``
```blocks
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
        if(cakLandSonar.isSonar(cakLandSonar.Comparison.Closer,30)){
        cakLandMotor.stop()
        basic.pause(1000)
    }
})
```
## @showhint
Create a ``||functions:function||`` and name it ``||functions:react||``
```blocks
function react(){
}
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
        if(cakLandSonar.isSonar(cakLandSonar.Comparison.Closer,30)){
        cakLandMotor.stop()
        basic.pause(1000)
    }
})
```
## @showhint
Add a numeric parameter "degrees" to be passed in the ``||functions:react function||``
```blocks
function react(degrees:number){
}
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
        if(cakLandSonar.isSonar(cakLandSonar.Comparison.Closer,30)){
        cakLandMotor.stop()
        basic.pause(1000)
    }
})
```
## @showhint
Nest ``||cakLandServos:turn servo at P1 to degrees:||`` ``||degrees||`` under
``||Functions:function react||``
```blocks
function react(degrees:number){
    cakLandServos.turnServo(cakLandServos.ServoPin.P1,degrees)
}
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
        if(cakLandSonar.isSonar(cakLandSonar.Comparison.Closer,30)){
        cakLandMotor.stop()
        basic.pause(1000)
    }
})
```
## @showhint
Add two ``||basic:pause||`` blocks. One after the ``||cakLandServos:turn servo at P1 to degrees:||`` 
and another one after ``||cakLandMotor:turn left motor at speed -30||``
```blocks
function react(degrees:number){
    cakLandServos.turnServo(cakLandServos.ServoPin.P1,degrees)
    basic.pause(1000)
    cakLandMotor.turnLeft(-30)
    basic.pause(2500)
}
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
        if(cakLandSonar.isSonar(cakLandSonar.Comparison.Closer,30)){
        cakLandMotor.stop()
        basic.pause(1000)
    }
})
```
## @showhint
Add a ``||cakLandMotor:stop motors||`` 
```blocks
function react(degrees:number){
    cakLandServos.turnServo(cakLandServos.ServoPin.P1,degrees)
    basic.pause(1000)
    cakLandMotor.turnLeft(-30)
    basic.pause(2500)
    cakLandMotor.stop()
}
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
        if(cakLandSonar.isSonar(cakLandSonar.Comparison.Closer,30)){
        cakLandMotor.stop()
        basic.pause(1000)
    }
})
```
## @showhint
Add a ``||cakLandServos:turn servo at P1 to degrees: (35)||`` block under the ``||Functions:function react||``
also add two more ``||basic:pause||`` blocks and one ``||cakLandMotor:turn left motor at speed: (50)||``
```blocks
function react(degrees:number){
    cakLandServos.turnServo(cakLandServos.ServoPin.P1,degrees)
    basic.pause(1000)
    cakLandMotor.turnLeft(-30)
    basic.pause(2500)
    cakLandMotor.stop()
    cakLandServos.turnServo(cakLandServos.ServoPin.P1,35)
    basic.pause(1000)
    cakLandMotor.turnLeft(50)
    basic.pause(1000)
}
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
        if(cakLandSonar.isSonar(cakLandSonar.Comparison.Closer,30)){
        cakLandMotor.stop()
        basic.pause(1000)
    }
})
```
## @showhint
This is the final code
```blocks
function react (degrees: number) {
    cakLandServos.turnServo(cakLandServos.ServoPin.P1, degrees)
    basic.pause(1000)
    cakLandMotor.turnRight(-30)
    basic.pause(2500)
    cakLandMotor.stop()
    cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
    basic.pause(1000)
    cakLandMotor.turnRight(50)
    basic.pause(1000)
}
cakLandServos.turnServo(cakLandServos.ServoPin.P1, 35)
cakLandServos.motorPinPower(cakLandServos.MotorPin.Left, cakLandServos.Power.On)
cakLandMotor.turnRight(50)
basic.forever(function () {
    basic.pause(1000)
    cakLandSonar.graphSonar(50)
    if (cakLandSonar.isSonar(cakLandSonar.Comparison.Closer, 30)) {
        cakLandMotor.stop()
        basic.pause(1000)
        if (Math.randomBoolean()) {
            react(60)
        } else {
            react(10)
        }
    }
})
```