# DS18B20 Temperature Sensor Guide

This sensor communicates with the RPi through a 1-wire line.

#### Here's a table outlining the sensor pins and the RPi pins they connect to
|   DS18B20 Pins  | Raspberry Pi Pins |
|:---------------:|:-----------------:|
|   Right leg(S)  |       GPIO4       |
|   Left leg(-)   |        GND        |
| Middle leg(VCC) |         5V        |


The time between the `Python` script initiating a temperature conversion and obtaining a value is approximately 751 milliseconds. 
This follows the fact that the sensor's bit resolution affects its Temperature Conversion Time which is the bulk of the time step in concern.

#### Here is a table outlining Bit Resolutions with corresponding Conversion times and Value increments.
| Resolution in Bits | Maximum Temperature Conversion Time (ms) | Temperature Value Increments in Celcius |
|:------------------:|:----------------------------------------:|:---------------------------------------:|
|          9         |                   93.75                  |                   0.5                   |
|         10         |                   187.5                  |                   0.25                  |
|         11         |                    375                   |                  0.125                  |
|         12         |                    750                   |                  0.0625                 |

*It follows that a higher bit resolution takes more time yet provides more accuracy.*

You can read the [Sensor Documentation](https://datasheets.maximintegrated.com/en/ds/DS18B20.pdf)
