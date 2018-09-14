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
              
    d.
    
    e. When the flashlight from a smartphone is used to shine light on the LDR, the 10-bit value read from the corresponding                       channel is 1023. This is taken as the maximum value that can be read from the LDR
    
    # function to convert light to percentage, # places: number of decimal places needed

    def ConvertPercent(data, places):
           percent = (data * 100) / float(1023)     #first convert the value/light to a percentage
           percent = round(percent, places)         #round the value to places number of decimal places
           return percent                           #return the required value
