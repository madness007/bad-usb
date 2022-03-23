# bad-usb

A bad usb project created by https://arnoschoutteten.be

## project description

This bad usb doesn't have flash storage, such as other regular sticks. This stick has a ATMEGA32U4 microprocessor, which can act as a mouse or keyboard.

You can download scripts and run them with the highest privileges!

This project is based on a "Atmega 32u4 microprocessor".
[Aliexpress search](https://nl.aliexpress.com/wholesale?catId=0&initiative_id=SB_20220323085714&SearchText=atmega+32u4+usb)

More info about the microprocessor [here](https://www.arduino.cc/reference/en/libraries/keyboardazertyfr/)


## installation

This project is made in the arduino ide.

* open the running project in the arduino ide
* tools -> device -> arduino micro
* install the [keyboardAzertyFr library](https://www.arduino.cc/reference/en/libraries/keyboardazertyfr/)
* press upload  

## sample code (rickroll)

```arduino
#include <KeyboardAzertyFr.h>

void setup() {
  KeyboardAzertyFr.begin();
  delay(800);

  runBox();
  printStr("cmd /c start https://www.youtube.com/watch?v!dQw4w9WgXcQ");
  enter();
  delay(5000);
  runBox();
  delay(100);
  printStr("notepad");
  enter();
  printStr("Deze USB heeft geen flash storage zoals iedere andere USB-Stick.");
  enter();
  printStr("In deze stick zit een Atmel ATMEGA32U4 microprocessor.");
  enter();
  printStr("Deze microprocessor kan een muis en toetsenbord emuleren.");
  enter();
  printStr("Omdat windows toetsenborden vertrouwd(als gebruiker), kan ik via een scriptje alle keystrokes injecteren in hoogstens een paar seconden.");
  enter();
  printStr("Zo kan ik bijvoorbeeld een Bash of Powershell script downloaden via internet en alles uitvoeren wat ik maar wil!");   
  enter();
  printStr("Een gevaarlijke tool dus!!");   
  enter();
  printStr("Deze stick zal enkel worden gebruikt voor automatisatie en educatie."); 
  fullScreen(); 
}

void loop() {
  // put your main code here, to run repeatedly:
}

void printStr(String str){
  for(int i = 0; i < str.length(); i++ ){
    KeyboardAzertyFr.press(str[i]);
    delay(5);
    KeyboardAzertyFr.releaseAll();
    delay(1);
  }
}

void runBox(){
  KeyboardAzertyFr.press(KEY_LEFT_GUI);
  KeyboardAzertyFr.press('r');
  delay(50);
  KeyboardAzertyFr.releaseAll();
  }
  
void enter(){
  KeyboardAzertyFr.press(KEY_RETURN);
  delay(10);
  KeyboardAzertyFr.releaseAll();
  delay(50);
  }

 void fullScreen(){
  KeyboardAzertyFr.press(KEY_LEFT_GUI);
  KeyboardAzertyFr.press(KEY_UP_ARROW);
  delay(50);
  KeyboardAzertyFr.releaseAll();
  }

```