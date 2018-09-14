TSENGWA KUKHOKUHLE                                           TSNKUK001
DANCAN ANGWENYI                                              ANGDAN002
Practical 4: RPI-3B SPI and Interrupt
(RPI-Python Serial Com. and RPI-Python Interrupt)

1.	a.

    b.
    
    c.
    
    # function to convert data to voltage level, # places: number of decimal places needed
    def ConvertVolts(data, places):
              volts  =  (data * 3.3) / float(1023)      #first convert the data to a value between 0 V and 3.3 V
              volts  =  round(volts, places)            #round the floating point number to placesnumber of decimal places
              return volts                              #return the required value   
              
    d. From the datasheet of the MCP9700A temperature sensor by Microchip technology, there is a linear relationship between            the output voltage of the sensor and the temperature in degrees Celsius. This relationship is found from Figure 2-16 of the     datasheet to be:
    
    # function to convert a 10-bit temperature value to degrees Celsius, # places: number of decimal places needed
    def ConvertDegCel(data, places):
               vout = ConvertVolts(data, 2)        #first convert the 10 bit number to a voltage with two decimal places
               temp = ( 100*vout ) - 50            #convert the output voltage to a temperature using the information from the      datasheeet
               return temp                         #return the temperature
    
    e. When the flashlight from a smartphone is used to shine light on the LDR, the 10-bit value read from the corresponding                       channel is 1023. This is taken as the maximum value that can be read from the LDR
    
    # function to convert light to percentage, # places: number of decimal places needed

    def ConvertPercent(data, places):
           percent = (data * 100) / float(1023)     #first convert the value/light to a percentage
           percent = round(percent, places)         #round the value to places number of decimal places
           return percent                           #return the required value
