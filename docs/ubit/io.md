#uBit.io

##Overview

##Message Bus ID

##Message Bus Events

#API
[comment]: <> ({"className":"MicroBitPin"})
##Constructor
<br/>
####MicroBitPin( <div style='color:#008080; display:inline-block'>int</div> id,  <div style='color:#008080; display:inline-block'>PinName</div> name,  <div style='color:#008080; display:inline-block'>PinCapability</div> capability)
#####Description
Constructor. Create a Button representation with the given ID.  MicroBitPin
#####Parameters

>  <div style='color:#008080; display:inline-block'>int</div> *id* - the ID of the new Pin object. 

>  <div style='color:#008080; display:inline-block'>PinName</div> *name* - the pin name for this  MicroBitPin  instance to represent 

>  <div style='color:#008080; display:inline-block'>PinCapability</div> *capability* - the capability of this pin.
#####Example
```c++
 MicroBitPin P0(MICROBIT_ID_IO_P0, MICROBIT_PIN_P0, PIN_CAPABILITY_BOTH); 

```
##setDigitalValue
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> setDigitalValue( <div style='color:#008080; display:inline-block'>int</div> value)
#####Description
Configures this IO pin as a digital output (if necessary) and sets the pin to 'value'. 
#####Parameters

>  <div style='color:#008080; display:inline-block'>int</div> *value* - 0 (LO) or 1 (HI) 
#####Returns
MICROBIT_OK on success, MICROBIT_INVALID_PARAMETER if value is out of range, or MICROBIT_NOT_SUPPORTED if the given pin does not have digital capability.
#####Example
```c++
 MicroBitPin P0(MICROBIT_ID_IO_P0, MICROBIT_PIN_P0, PIN_CAPABILITY_BOTH); 
 P0.setDigitalValue(1); // P0 is now HI 

```
##getDigitalValue
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> getDigitalValue()
#####Description
Configures this IO pin as a digital input (if necessary) and tests its current value. 
#####Returns
1 if this input is high, 0 if input is LO, or MICROBIT_NOT_SUPPORTED if the given pin does not have analog capability.
#####Example
```c++
 MicroBitPin P0(MICROBIT_ID_IO_P0, MICROBIT_PIN_P0, PIN_CAPABILITY_BOTH); 
 P0.getDigitalValue(); // P0 is either 0 or 1; 

```
##setAnalogValue
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> setAnalogValue( <div style='color:#008080; display:inline-block'>int</div> value)
#####Description
Configures this IO pin as an analog/pwm output, and change the output value to the given level. 
#####Parameters

>  <div style='color:#008080; display:inline-block'>int</div> *value* - the level to set on the output pin, in the range 0 - 1024 
#####Returns
MICROBIT_OK on success, MICROBIT_INVALID_PARAMETER if value is out of range, or MICROBIT_NOT_SUPPORTED if the given pin does not have analog capability.
##setServoValue
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> setServoValue( <div style='color:#008080; display:inline-block'>int</div> value)
#####Description
Configures this IO pin as an analog/pwm output if it isn't already, configures the period to be 20ms, and sets the duty cycle between 0.05 and 0.1 (i.e. 5% or 10%) based on the value given to this method.
#####Parameters

>  <div style='color:#008080; display:inline-block'>int</div> *value* - the level to set on the output pin, in the range 0 - 180 
#####Returns
MICROBIT_OK on success, MICROBIT_INVALID_PARAMETER if value is out of range, or MICROBIT_NOT_SUPPORTED if the given pin does not have analog capability. 
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> setServoValue( <div style='color:#008080; display:inline-block'>int</div> value,  <div style='color:#008080; display:inline-block'>int</div> range)
#####Description
Configures this IO pin as an analog/pwm output if it isn't already, configures the period to be 20ms, and sets the duty cycle between 0.05 and 0.1 (i.e. 5% or 10%) based on the value given to this method.
#####Parameters

>  <div style='color:#008080; display:inline-block'>int</div> *value* - the level to set on the output pin, in the range 0 - 180 

>  <div style='color:#008080; display:inline-block'>int</div> *range* - which gives the span of possible values the i.e. lower and upper bounds center  range/2 (Defaults to: MICROBIT_PIN_DEFAULT_SERVO_RANGE) 
#####Returns
MICROBIT_OK on success, MICROBIT_INVALID_PARAMETER if value is out of range, or MICROBIT_NOT_SUPPORTED if the given pin does not have analog capability. 
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> setServoValue( <div style='color:#008080; display:inline-block'>int</div> value,  <div style='color:#008080; display:inline-block'>int</div> range,  <div style='color:#008080; display:inline-block'>int</div> center)
#####Description
Configures this IO pin as an analog/pwm output if it isn't already, configures the period to be 20ms, and sets the duty cycle between 0.05 and 0.1 (i.e. 5% or 10%) based on the value given to this method.
#####Parameters

>  <div style='color:#008080; display:inline-block'>int</div> *value* - the level to set on the output pin, in the range 0 - 180 

>  <div style='color:#008080; display:inline-block'>int</div> *range* - which gives the span of possible values the i.e. lower and upper bounds center  range/2 (Defaults to: MICROBIT_PIN_DEFAULT_SERVO_RANGE) 

>  <div style='color:#008080; display:inline-block'>int</div> *center* - the center point from which to calculate the lower and upper bounds (Defaults to: MICROBIT_PIN_DEFAULT_SERVO_CENTER) 
#####Returns
MICROBIT_OK on success, MICROBIT_INVALID_PARAMETER if value is out of range, or MICROBIT_NOT_SUPPORTED if the given pin does not have analog capability. 
##getAnalogValue
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> getAnalogValue()
#####Description
Configures this IO pin as an analogue input (if necessary and possible). 
#####Returns
the current analogue level on the pin, in the range 0 - 1024, or MICROBIT_NOT_SUPPORTED if the given pin does not have analog capability.
#####Example
```c++
 MicroBitPin P0(MICROBIT_ID_IO_P0, MICROBIT_PIN_P0, PIN_CAPABILITY_BOTH); 
 P0.getAnalogValue(); // P0 is a value in the range of 0 - 1024 

```
##isInput
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> isInput()
#####Description
Determines if this IO pin is currently configured as an input. 
#####Returns
1 if pin is an analog or digital input, 0 otherwise. 
##isOutput
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> isOutput()
#####Description
Determines if this IO pin is currently configured as an output. 
#####Returns
1 if pin is an analog or digital output, 0 otherwise. 
##isDigital
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> isDigital()
#####Description
Determines if this IO pin is currently configured for digital use. 
#####Returns
1 if pin is digital, 0 otherwise. 
##isAnalog
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> isAnalog()
#####Description
Determines if this IO pin is currently configured for analog use. 
#####Returns
1 if pin is analog, 0 otherwise. 
##isTouched
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> isTouched()
#####Description
Configures this IO pin as a makey makey style touch sensor (if necessary) and tests its current debounced state. 
#####Returns
1 if pin is touched, 0 if not, or MICROBIT_NOT_SUPPORTED if this pin does not support touch capability.
#####Example
```c++
 MicroBitPin P0(MICROBIT_ID_IO_P0, MICROBIT_PIN_P0, PIN_CAPABILITY_ALL); 
 if(P0.isTouched()) 
 { 
 uBit.display.clear(); 
 } 

```
##setServoPulseUs
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> setServoPulseUs( <div style='color:#008080; display:inline-block'>int</div> pulseWidth)
#####Description
Configures this IO pin as an analog/pwm output if it isn't already, configures the period to be 20ms, and sets the pulse width, based on the value it is given
#####Parameters

>  <div style='color:#008080; display:inline-block'>int</div> *pulseWidth* - the desired pulse width in microseconds. 
#####Returns
MICROBIT_OK on success, MICROBIT_INVALID_PARAMETER if value is out of range, or MICROBIT_NOT_SUPPORTED if the given pin does not have analog capability. 
##setAnalogPeriod
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> setAnalogPeriod( <div style='color:#008080; display:inline-block'>int</div> period)
#####Description
Configures the PWM period of the analog output to the given value.
#####Parameters

>  <div style='color:#008080; display:inline-block'>int</div> *period* - The new period for the analog output in milliseconds. 
#####Returns
MICROBIT_OK on success, or MICROBIT_NOT_SUPPORTED if the given pin is not configured as an analog output.
##setAnalogPeriodUs
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> setAnalogPeriodUs( <div style='color:#008080; display:inline-block'>int</div> period)
#####Description
Configures the PWM period of the analog output to the given value.
#####Parameters

>  <div style='color:#008080; display:inline-block'>int</div> *period* - The new period for the analog output in microseconds. 
#####Returns
MICROBIT_OK on success, or MICROBIT_NOT_SUPPORTED if the given pin is not configured as an analog output. 
##getAnalogPeriodUs
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> getAnalogPeriodUs()
#####Description
Retrieves the PWM period of the analog output.
#####Returns
the period on success, or MICROBIT_NOT_SUPPORTED if the given pin is not configured as an analog output. 
##getAnalogPeriod
<br/>
####<div style='color:#FF69B4; display:inline-block'>int</div> getAnalogPeriod()
#####Description
Retrieves the PWM period of the analog output.
#####Returns
the period on success, or MICROBIT_NOT_SUPPORTED if the given pin is not configured as an analog output. 
____
[comment]: <> ({"end":"MicroBitPin"})