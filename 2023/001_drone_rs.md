
# Droners

In this blog we will see an overview of the [Droners](https://github.com/abishekatp/drone-rs) project.


## Microcontroller

Arduino UNO(ATmega328P)

Digital pins
Can deliver 5V on each of the digital pin of the board from d0 to d13. Digital pin 13 is connected with built-in LED.

Analog pins
There are 6 analog pins from a0 to a5. Arduino boards contain a multichannel, 10-bit analog to digital converter. This means that it will map input voltages between 0 and the operating voltage(5V or 3.3V) into integer values between 0 and 1023.




## Battery

3-cell 11.1V 30C LiPo battery 1800mAh


### How can we indicate the low battery to the users?

One useful thing to remember is that as you use the battery power its voltage will drop from its fully charged voltage to some nominal voltage. Using this we can alert the user about the low battery power. But we can't directly read it from the battery. So we will use voltage divider with two resister to measure this voltage.
![voltage divider circuit](/2023/images/voltage_divider.png "Voltage divider")


* So using the above property of the batteries we can measure the low power status of the battery using a simple trick. For exmaple consider a 3-cell 11.1V battery. After it uses its 80% of its power it will drop from 11.1V to some lower voltage(may be to the 9V). We can measure this voltage drop to indicate the user about the battery level.

Since Arduino board can only handle maximum of 5V, we can't directly connect the battery output to the Arduino. If you do, then it will damage the board. So we can use the behaviour of the above voltage divider circuit to measure the battery voltage in a safe way. We can connect the $V_o$ to the arduino analog pin to measure the battery voltage. As long as we supply maximum of 5V to the Arduino board the current $i_o$ will be 0. We will see soon that we can set the values of $R_1$ and $R_2$ such that the value of $V_o$ will be always less than 5V. To find a suitable values for $R_1$ and $R_2$ first we have to understand the following formulas. These formulas uses the basic Ohms formula V=IR.

$$
 i = \frac{V_i}{R_1 + R_2} \\
 
 V_o = i \times R_2 = \frac{V_i \times R_2}{R_1 + R_2}
$$

Now assume the following values for each of the circuit elements. $V_i = 12, R_1=1000\Omega, R_2 = 2000\Omega$.

$$
 i =  \frac{12}{3000} = 4 \times 10^{-3}A \\
 
 V_o = \frac{12 \times 2000}{3000} = 8V
$$

Now assume the following values for each of the circuit elements. $V_i = 12, R_1=2000\Omega, R_2 = 1000\Omega$.

$$
 i =  \frac{12}{3000} = 4 \times 10^{-3}A \\
 
 V_o = \frac{12 \times 1000}{3000} = 4V
$$
So this combination will work for us. So in our voltage divider circuit we can use the value $R_1=2000\Omega, R_2 = 1000\Omega$.


## ESC

30A ESC(Electronic speed controllers)



## Motor

A2212 / 8T 1800KV BLDC(brushless DC motor)






## Accelerometer and Gyroscope

GY-521 MPU-6050 MPU6050 3 Axis Accelerometer Gyroscope Module 6 DOF 6-Axis Accelerometer Gyroscope Sensor Module 16 Bit Ad Converter. This sensor has Supply voltage: 3.3-5VDC. Signal voltage: 3.3VDC.






## Project setup:
- Installing needed third party toolchains for mac - 
```
xcode-select --install # for the fist time
brew tap osx-cross/avr
brew install avr-binutils avr-gcc avrdude
```
- Install the ravedude rust crate: 
```
cargo +stable install ravedude
```
- To get this basic template we have used:
```
cargo install cargo-generate
cargo generate --git https://github.com/Rahix/avr-hal-template.git
```
References:
https://medium.com/@ninjapiraatti/programming-arduino-with-rust-on-mac-7c7536f3973d
https://blog.logrocket.com/complete-guide-running-rust-arduino/