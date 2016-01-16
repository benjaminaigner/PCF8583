# PCF8583 - RTC calendar with alarm function

Original source from Erik DeBill ( https://github.com/edebill/PCF8583 ).

This version extends the original one by a 2nd constructor to support a different configuration.

# Usage

`
    //init the PCF8583 & the TWI interface.
    //Adress is either 0xA0 (pin A0 -> GND) or 0xA1 (pin A0 -> VCC)
    PCF8583 pcf(0xA0);
    
    //If you prefer to use another configuration
    //e.g. 50Hz clock (retrieved from the mains)
    //use the other constructor with a give configuration byte
    PCF8583 pcf(0xA0,0x10);
    
    
    //Fetch the current time
    pcf.get_time();

    //Extract the year
    Serial.print("year: ");
    Serial.println(pcf.year);

    //Update each value of the PCF object
    pcf.hour = 14;
    pcf.minute = 30;
    pcf.second = 0;
    pcf.year = 2009;
    pcf.month = 9;
    pcf.day = 12;
    
    //set the PCF8583 internal date/time
    pcf.set_time();

`