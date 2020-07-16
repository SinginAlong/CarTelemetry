# CarTelemetry

## Goal
Hope to use an RPi, a GPS and a IMU to accurately track a car on the road or track

## Materials
Adafruit Ultimate GPS V3 (possibly with different antenna)
Adafruit BNO055 IMU
Raspberry PI 3 (don't need the power of the 4)

## PCB Board Requirements
- PCB will mount on RPi, including using screws
- GPS and IMU will mount on top of board (may use screw holes)
- Final assembly must be securable to a surface in an enclosure box
- Board will take 12V from car, clean it (de-surge, de-dip), and regulate it to 5V
- Board will pass ignition line to RPi, with protections


## PCB Board Connections

### Car
- Power in (from battery, never shuts off)
- Ignition in (goes high when car electronics are on, low when car is shut off)
- Ground

### Ultimate GPS
- VIN (3-5VDC)
- Ground
- VBAT (3.3 power to GPS RTC) (run from car batt with long (month) timer?)
- EN (enable), ground to shut off GPS (use when ignition is lost?)
- 3.3V out (if you need 3.3 volts)
- TX 
- RX
- Fix (pulses low high when no fix, stays low for 15 seconds when fixed)
- PPS (pulse per second, for timing)

### BNO055 IMU
- VIN (3.3 to 5 V)
- 3VO (3.3 volts out from reg, 50ma available)
- GND
- SCL (i2c clock pin)
- SDA (i2c data pin)
- RST, hardware reset (low then high, 5V safe)
- INT, interrput output pin, 3V
- ADR, set high to change i2c address from 0x28 to 0x29
- PS0, PS1 (config stuff, don't connect)

### RPi
- all the pins


## TODO
- Write down vision for project
- Create requirements for board
- List limitations from environment
- Start designing board in Eagle CAD
