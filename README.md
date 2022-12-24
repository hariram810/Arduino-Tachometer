# Arduino-Tachometer

![Screenshot (745)](https://user-images.githubusercontent.com/118633170/209418617-04df2325-0347-41fe-a691-2030ca60381c.png)

If you have hard-time 3d printing stuff and other materials which i have provided in this project please refer the professionals for the help, [JLCPCB](https://jlcpcb.com/RNA) is one of the best company from shenzhen china they provide, PCB manufacturing, PCBA and 3D printing services to people in need, they provide good quality products in all sectors

[JLCPCB](https://jlcpcb.com/RNA)


Please use the following link to register an account in [JLCPCB](https://jlcpcb.com/RNA)

https://jlcpcb.com/RNA



Pcb Manufacturing

----------

2 layers

4 layers

6 layers

jlcpcb.com/RNA



PCBA Services

[JLCPCB](https://jlcpcb.com/RNA) have 350k+ Components In-stock. You don’t have to worry about parts sourcing, this helps you to save time and hassle, also keeps your costs down.

Moreover, you can pre-order parts and hold the inventory at [JLCPCB](https://jlcpcb.com/RNA), giving you peace-of-mind that you won't run into any last minute part shortages. jlcpcb.com/RNA



3d printing

-------------------

SLA -- MJF --SLM -- FDM -- & SLS. easy order and fast shipping makes [JLCPCB](https://jlcpcb.com/RNA) better companion among other manufactures try out [JLCPCB](https://jlcpcb.com/RNA) 3D Printing servies

[JLCPCB](https://jlcpcb.com/RNA) 3D Printing starts at $1 &Get $54 Coupons for new users

The Tachometer is an RPM counter which counts the no. of rotation per minute. There are two types of tachometer one mechanical and another one is digital. Here we are going to design an Arduino-based digital tachometer using an IR sensor module to detect objects for count rotation of any rotating body. IR transmits IR rays which reflect back to the IR receiver and then IR Module generates an output or pulse which is detected by the Arduino controller when we press the start button. It counts continuously for 5 seconds.

![Screenshot (747)](https://user-images.githubusercontent.com/118633170/209418678-3aed8050-9684-4265-b3f2-6edf1016de60.png)


You can also make: Fan Speed Measurement Device as well as GPS Speedometer.

An infrared sensor is an electronic instrument that is used to sense certain characteristics of its surroundings by either emitting and/or detecting infrared radiation. Infrared sensors are also capable of measuring the heat being emitted by an object and detecting motion.

The wavelength region which ranges from 0.75 to 3µm is known as the near-infrared region. The region between 3 and 6µm is known as the mid-infrared and infrared radiation which has a wavelength greater higher than 6µm is known as far-infrared.

An IR sensor consists of an IR LED and an IR Photodiode; together they are called Photo–Coupler or Opto–Coupler. As said before, the Infrared Obstacle Sensor has a built-in IR transmitter and IR receiver. An infrared Transmitter is a light-emitting diode (LED) that emits infrared radiation. Hence, they are called IR LEDs. Even though an IR LED looks like a normal LED, the radiation emitted by it is invisible to the human eye. Infrared receivers are also called infrared sensors as they detect the radiation from an IR transmitter. IR receivers come in the form of photodiodes and phototransistors. Infrared Photodiodes are different from normal photodiodes as they detect only infrared radiation. When the IR transmitter emits radiation, it reaches the object and some of the radiation reflects back to the IR receiver. Based on the intensity of the reception by the IR receiver, the output of the sensor is defined.

his sensor uses an infrared LED on one side, and there is a photosensor on another side. So when there’s no obstacle between these sides the infrared light reaches the photosensor and gives the signal to the circuit. And this module will output 5V or HIGH state.

But the opposite, if there’s an obstacle between these sides, the photosensor will not detect light and no signal given to the circuit. So the output of this module will be LOW.

So the conclusion is, if there’s an obstacle it will output HIGH

output pin is directly connected to pin 18 (A4). Vcc and GND are connected to Vcc and GND of arduino. A 16x2 LCD is connected with arduino in 4-bit mode. Control pin RS, RW and En are directly connected to arduino pin 2, GND and 3. And data pin D4-D7 is connected to pins 4, 5, 6 and 7 of arduino. A push button is also added in this project. When we need to count RPM we press this button to start this Arduino Tachometer to count RPM for five seconds. This push button is connected to pin 10 of arduino with respect to ground. You can learn more about the working of IR transmitter and receiver

![Screenshot (746)](https://user-images.githubusercontent.com/118633170/209418673-dbcf9375-1a73-482f-aa39-ba51193d3640.png)

The unit of measurement of the tachometer is the revolutions per minute (RPM), since you have to understand that revolutions mean turns, then it would be the number of turns that the element makes, for each minute.

The word tachometer has an origin in the Greek vocabulary, the prefix “Tacko” means speed or high speed and for its part, the suffix “Metron” is translated as measure. So, this is why I affirm that the tachometer is an instrument that measures speed.

This DIY Tachometer is cheap and works with the principle of Infrared waves. Infrared waves has wavelength longer than the visible light, so they are not visible to our human eyes.

![Screenshot (748)](https://user-images.githubusercontent.com/118633170/209418682-fcd10b21-5cb9-45ce-b5d6-3fd22353262f.png)

Here we are using an IR sensor module which contains two IR LEDs, one is to emit the IR rays which is called IR Transmitter, and another IR LED which is also called as IR Photo Diode which acts as a IR rays receiver or IR sensor.

![Screenshot (749)](https://user-images.githubusercontent.com/118633170/209418696-02e441b6-6387-4011-93e6-7803bde32038.png)


IR transmitter LED looks same as normal LED but the IR rays emitted through it are not visible to human eyes, and IR receivers comes in the forms of photo diodes which are not same as normal Photo diodes as IR diodes receive only InfraRed rays.

When the IR sensor module is powered on, IR transmitter emits IR rays and reaches to an object in front of it and few amount of IR rays are reflected back and according to the intensity of the received rays the IR receiver receives the IR rays and generate the voltage and outputs it through the OUT pin with the help of LM358 IC.

From the above wiring diagram you can see the IR sensor and LCD display VCC and GND are powered from 5V and GND pins of Arduino respectively. The OUT pin from the IR sensor module is connected to the digital pin 2 on Arduino. SDA and SCL pins from the LCD display are connected to A4 and A5 of Arduino respectively. That’s it for connection now lets upload the below code and see how this works below.

![Screenshot (751)](https://user-images.githubusercontent.com/118633170/209418700-37e8a383-f2f4-4001-9d1f-59269744b371.png)


#include <LiquidCrystal.h>

LiquidCrystal lcd(7, 6, 5, 4, 3, 2);

#define sensor 9

#define start 12

int delay1()

{

//unsigned int long k;

int i,j;

unsigned int count=0;

for(i=0;i<1000;i++)

{

for(j=0;j<1000;j++)

{

if(digitalRead(sensor))

{

count++;

while(digitalRead(sensor));

}

}

}

return count;

}

void setup()

{

pinMode(sensor, INPUT);

pinMode(start, INPUT);

pinMode(2, OUTPUT);

lcd.begin(16, 2);

lcd.print(” Tachometer”);

delay(2000);

digitalWrite(start, HIGH);

}

void loop()

{

unsigned int time=0,RPM=0;

lcd.clear();

lcd.print(” Please Press “);

lcd.setCursor(0,1);

lcd.print(“Button to Start “);

while(digitalRead(start));

lcd.clear();

lcd.print(“Reading RPM…..”);

time=delay1();

lcd.clear();

lcd.print(“Please Wait…..”);

RPM=(time*12)/3;

delay(2000);

lcd.clear();

lcd.print(“RPM=”);

lcd.print(RPM);

delay(5000);

}

![Screenshot (758)](https://user-images.githubusercontent.com/118633170/209418704-6bc5a479-60fa-42df-a815-639f896b8a01.png)

After uploading the code when this device is powered on the, IR sensor’s IR transmitter transmits the IR rays and when an object comes in front of the sensor at a certain distance which can be adjusted with the help of onboard 1k potentiometer, these rays will get reflected back to the sensor photo diode which receives only IR waves and generates a voltage signal which outputs through the output pin as digital output with the help of LM358 IC.

According to the IR sensor working when an object comes in front of the emitted rays the sensor detects it as an obstacle and signal led lights up, and outputs a signal through OUT pin. When a rotating object rotates, for example a fan which has 3 wings rotates if we place the sensor in front of the rotating wings the sensor detects the wings and we can count the number of times the wings comes as obstacle before the sensor.

This output pin is connected to one of the digital pins of Arduino, with the help of interrupts and calculating the time, we can get the RPM value of the rotating object.
