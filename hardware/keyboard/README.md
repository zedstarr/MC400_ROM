Keyboard matrix decoded with the help of Frank Adams' Teensyduino sketch from https://github.com/thedalles77/USB_Laptop_Keyboard_Controller


![MC400 keyboard matrix](https://github.com/zedstarr/MC400_ROM/raw/main/hardware/keyboard/Screenshot%20from%202022-08-23%2015-29-46.png)

Matrix available in the .ino code or in the .xlsx file ;-) 

The "ESC" key (which is also the "On" key) is unique in that it has 2 dedicated lines to ASIC2, obviously needed as when the hw is "off" as it's not scanning the whole keyboard.

Of the 18 pins on the main keyboard it's a 9x9 matrix, but pins 1 & 2 are dedicated to "On/ESC" so it's 8x8 for the other 60 keys.

The supplementary case mounted buttons (Task/Del/Home/End/PgUp/PgDn/LCD/Rec) are not covered by this sketch

Teensy LC sketch included here

Further details here: https://zedstarr.com/2022/06/20/repurposing-an-old-psion-mc400-laptop-keyboard-with-teensyduino-usb/

