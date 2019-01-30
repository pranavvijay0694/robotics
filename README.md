#### WELCOME TO WORK SHOP
## ARDUINO

  It is an open-source platform used for building electronics projects. Arduino consists of both a physical programmable circuit board (often referred to as a microcontroller) and a piece of software, or IDE (Integrated Development Environment) that runs on your computer, used to write and upload computer code to the physical board.

## Blinking  LED



<img src="https://lh3.googleusercontent.com/7Gk9LGjB8oSRRnKOsgfddZRuFhcpxEGdFEwiiCfrtyqdKdMGDZpU02WeXM4WYj6hhmDW9_uA-2YzPB1SgypiaFl_v5NzodoKk7wrzNuNj9-n9aa_elyO0ix-n9KO3sG4lzpnBclfn1oICJ7mMh4CrsQrhk0oOEo76aRcvEIrOMzxDmItsnVwJu6WvstX-vUb4acjPOtacNggFPcQX5uGhQuYnkGgdljMBLjEBxWvsNjl8SmgweX5r5F5k0vMvkTrlh8YHJlI9qsb_FRaGfRNX0zlgyHJYn6Nj2etc_vB07b4dNYz6FAhwiX801W3DnvrBjO6ZTfEcyjVqIjJBXtE-2_IP24_OIA4r27QnUT4VnmKA0hTcefUp8rYmkujUnvuweoHVKZW6iwXBwfeVHCiVaqnqdshXafAuESWrkPsQ2UXJo-gmfRnTOO3LvY1Q3pKWgwo061zhekpcRPwdlnNYG6o08G5IE7D7tk-ZZvbfhz6mEDKCaKpZ5xzG_gjD4-DvoKksu2jvyprtFKoRhNNUGmJxrWlayGa3OPABvM9_0tFXav6fcBcWqteiR9F2gvXC3s6frwC9fQ7EabwYyhN9mzZ6B99cdCrfT2vYCoO9gbBte-qdu5KxOjVaqB8yg_o38HTlqXR_-oDeGF7BMESV3g=w676-h711-no">

```markdown

void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(13, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);                       // wait for a second
  digitalWrite(13, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);                       // wait for a second
}
```
### ACCELEROMETER


<img src="https://lh3.googleusercontent.com/dbptci5bvODfZZYAILXxJtp-GfqF3eQxjrSW4plfqt65JZk9E42KTC_iSSm80GrSqD45oFlsUaYolk1zzg3FpwbRjJBqdICrO5YcF1nDwy-Kr6dQ8T0G8KdT4Yrsju0euaZdBp8XKB2QavkxKoeR7SYXkBtAQC9oBXJ7G3nzlHYMtmnOXXhh7-271BLyIQ1o_-wUke_g-N4BypAczb2NkALDtS6gyCZGr5cEDJFLMQREUvFUHP5tTMBQmmPIB4hYOpdt79wRSHoM9NVZeFrYAQklDFYMX-cwu-yJSXIl0-7Uuh7OaC18tKKBIYCUE5jOLV3cyUcKj8EHSUD3UJ_jgLvlmtJG2H4T20HhGF1knwb6zykBm1hCp7WBUCkhACyd8Jto1r-mLL_h-aBFis1ulyKCi_HcGmfUE31W5DBmUEMvsUpLW4B83xsTKuQI_mbC5NCksGlQBWXEbb2MKUWXI93Sk75BZqPKPrBeHLRyiIYmWoMJGFWuULERkMu2a61sMrYKADzR2H9d_Bf9ON2Bunk1lcTxGbJK1Vkged2YlK7ugBH78LFQfRQLjGZf_LyvE84ia__PuAP3ujjJFVexjHhASU-soeE2ako7TxYkfE1XOHYag2Siuy7wwxmvGrHFCLFEmNlDdNnYkwR66DND2Sc=w352-h280-no" height="300" width="1500" >



```markdown


#include <Wire.h>
#include <Adafruit_Sensor.h>
#include <Adafruit_ADXL345_U.h>

/* Assign a unique ID to this sensor at the same time */
Adafruit_ADXL345_Unified accel = Adafruit_ADXL345_Unified(12345);

void displaySensorDetails(void)
{
  sensor_t sensor;
  accel.getSensor(& sensor);
  Serial.println("------------------------------------");
  Serial.print  ("Sensor:       "); Serial.println(sensor.name);
  Serial.print  ("Driver Ver:   "); Serial.println(sensor.version);
  Serial.print  ("Unique ID:    "); Serial.println(sensor.sensor_id);
  Serial.print  ("Max Value:    "); Serial.print(sensor.max_value); Serial.println(" m/s^2");
  Serial.print  ("Min Value:    "); Serial.print(sensor.min_value); Serial.println(" m/s^2");
  Serial.print  ("Resolution:   "); Serial.print(sensor.resolution); Serial.println(" m/s^2");  
  Serial.println("------------------------------------");
  Serial.println("");
  delay(500);
}

void displayDataRate(void)
{
  Serial.print  ("Data Rate:    "); 
  
  switch(accel.getDataRate())
  {
    case ADXL345_DATARATE_3200_HZ:
      Serial.print  ("3200 "); 
      break;
    case ADXL345_DATARATE_1600_HZ:
      Serial.print  ("1600 "); 
      break;
    case ADXL345_DATARATE_800_HZ:
      Serial.print  ("800 "); 
      break;
    case ADXL345_DATARATE_400_HZ:
      Serial.print  ("400 "); 
      break;
    case ADXL345_DATARATE_200_HZ:
      Serial.print  ("200 "); 
      break;
    case ADXL345_DATARATE_100_HZ:
      Serial.print  ("100 "); 
      break;
    case ADXL345_DATARATE_50_HZ:
      Serial.print  ("50 "); 
      break;
    case ADXL345_DATARATE_25_HZ:
      Serial.print  ("25 "); 
      break;
    case ADXL345_DATARATE_12_5_HZ:
      Serial.print  ("12.5 "); 
      break;
    case ADXL345_DATARATE_6_25HZ:
      Serial.print  ("6.25 "); 
      break;
    case ADXL345_DATARATE_3_13_HZ:
      Serial.print  ("3.13 "); 
      break;
    case ADXL345_DATARATE_1_56_HZ:
      Serial.print  ("1.56 "); 
      break;
    case ADXL345_DATARATE_0_78_HZ:
      Serial.print  ("0.78 "); 
      break;
    case ADXL345_DATARATE_0_39_HZ:
      Serial.print  ("0.39 "); 
      break;
    case ADXL345_DATARATE_0_20_HZ:
      Serial.print  ("0.20 "); 
      break;
    case ADXL345_DATARATE_0_10_HZ:
      Serial.print  ("0.10 "); 
      break;
    default:
      Serial.print  ("???? "); 
      break;
  }  
  Serial.println(" Hz");  
}

void displayRange(void)
{
  Serial.print  ("Range:         +/- "); 
  
  switch(accel.getRange())
  {
    case ADXL345_RANGE_16_G:
      Serial.print  ("16 "); 
      break;
    case ADXL345_RANGE_8_G:
      Serial.print  ("8 "); 
      break;
    case ADXL345_RANGE_4_G:
      Serial.print  ("4 "); 
      break;
    case ADXL345_RANGE_2_G:
      Serial.print  ("2 "); 
      break;
    default:
      Serial.print  ("?? "); 
      break;
  }  
  Serial.println(" g");  
}

void setup(void) 
{
#ifndef ESP8266
  while (!Serial); // for Leonardo/Micro/Zero
#endif
  Serial.begin(9600);
  Serial.println("Accelerometer Test"); Serial.println("");
  
  /* Initialise the sensor */
  if(!accel.begin())
  {
    /* There was a problem detecting the ADXL345 ... check your connections */
    Serial.println("Ooops, no ADXL345 detected ... Check your wiring!");
    while(1);
  }

  /* Set the range to whatever is appropriate for your project */
  accel.setRange(ADXL345_RANGE_16_G);
  // accel.setRange(ADXL345_RANGE_8_G);
  // accel.setRange(ADXL345_RANGE_4_G);
  // accel.setRange(ADXL345_RANGE_2_G);
  
  /* Display some basic information on this sensor */
  displaySensorDetails();
  
  /* Display additional settings (outside the scope of sensor_t) */
  displayDataRate();
  displayRange();
  Serial.println("");
  pinMode(12,OUTPUT);

}

void loop(void) 
{
  /* Get a new sensor event */ 
  sensors_event_t event; 
  accel.getEvent(&event);
 
  /* Display the results (acceleration is measured in m/s^2) */
  Serial.print("X: "); Serial.print(event.acceleration.x); Serial.print("  ");
  Serial.print("Y: "); Serial.print(event.acceleration.y); Serial.print("  ");
  Serial.print("Z: "); Serial.print(event.acceleration.z); Serial.print("  ");Serial.println("m/s^2 "); 
  delay(500);
  if(event.acceleration.x>0)
  {
    digitalWrite(12,HIGH);
  }
  else
  {
     digitalWrite(12,LOW);
  }
}
```
