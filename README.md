# A-Prototyping Hub

## Projects
### Pix3lone

This project is based for individuals who are interested to learn Microcontroller Programming.
This PCB design and built in Maldives for our market.

> Hardware Details and PIN Assignments

<img src="pixelone-02.png" width="500">

| ATMEGA32U4 PIN  | Arduino PIN Mapping  | Function Details |
| --------------- |:--------------------:|:----------------:|
| PD0             | 3                    | IO / SCL         |  
| PD1             | 2                    | IO / SDA         |         
| PD2             | 0                    | IO / Serial-RX   |
| PD3             | 1                    | IO / Serial-TX   |
| PD4             | 4                    | IO / ADC         |
| PD6             | 12                   | IO / ADC         |
| PD7             | 6                    | IO / ADC / PWM   |
| PC6             | 5                    | IO / PWM         |
| PF0             | A5                   | IO / ADC         |
| PF1             | A4                   | IO / ADC         |
| PF4             | A3                   | IO / ADC         |
| PF5             | A2                   | IO / ADC         |
| PF6             | A1                   | IO / ADC         |
| PF7             | A0                   | IO / ADC         |


There are many great README templates available on GitHub; however, I didn't find one that really suited my needs so I created this enhanced one. I want to create a README template so amazing that it'll be the last one you ever need -- I think this is it.

Here's why:
* Your time should be focused on creating something amazing. A project that solves a problem and helps others
* You shouldn't be doing the same tasks over and over like creating a README from scratch
* You should implement DRY principles to the rest of your life :smile:

> Hardware Details and PIN Assignments


```
void sendSensorValues()
{
  unxes[6], readings[5];
  byte sensorIndex;

  for (sensorIndex = 0; sensorIndex < 6; sensorIndex++) //for analog sensors, calculate the median of 5 sensor readings in order to avoid variability and power surges
  {
    for (byte p = 0; p < 5; p++)
      readings[p] = analogRead(sensorIndex);
    insertionSort(readings, 5); //sort readings
    sensorValues[sensorIndex] = readings[2]; //select median reading
  }

  //send analog sensor values
  for (sensorIndex = 0; sensorIndex < 6; sensorIndex++)
    ScratchBoardSensorReport(sensorIndex, sensorValues[sensorIndex]);

  //send digital sensor values
  ScratchBoardSensorReport(6, digitalRead(2)?1023:0);
  ScratchBoardSensorReport(10, digitalRead(3)?1023:0);
}

```
