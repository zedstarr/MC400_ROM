Keyboard matrix decoded with the help of Frank Adams' Teensyduino sketch from https://github.com/thedalles77/USB_Laptop_Keyboard_Controller


![MC400 keyboard matrix](https://zedstarr.files.wordpress.com/2022/06/screenshot-from-2022-06-19-21-50-17.png)

CSV table:  
``FPC pin,2,3,4,5,6,7,8,9,10,X,Y``  
``1,KEY_ESC,0,0,0,0,0,0,0,0,,``  
``11,0,0,KEY_1,KEY_3,KEY_5,KEY_7,KEY_9,KEY_MINUS,KEY_BACKSPACE,Task,Del``  
``12,0,0,KEY_2,KEY_4,KEY_6,KEY_8,KEY_0,KEY_EQUAL,KEY_TAB,Home,End``  
``13,0,0,KEY_Q,KEY_E,KEY_T,KEY_U,KEY_O,KEY_LEFT_BRACE,0,PgUp,PgDn``  
``14,0,KEY_CAPS_LOCK,KEY_W,KEY_R,KEY_Y,KEY_I,KEY_P,KEY_RIGHT_BRACE,KEY_BACKSLASH,LCD,Rec``  
``15,0,0,KEY_A,KEY_D,KEY_G,KEY_J,KEY_L,KEY_QUOTE,0,,``  
``16,0,0,KEY_S,KEY_F,KEY_H,KEY_K,KEY_SEMICOLON,KEY_TILDE,0,,``  
``17,0,KEY_LEFT,KEY_Z,KEY_C,KEY_B,KEY_M,KEY_PERIOD,KEY_UP,KEY_SPACE,,``  
``18,0,KEY_DOWN,KEY_X,KEY_V,KEY_N,KEY_COMMA,KEY_SLASH,KEY_ENTER,KEY_RIGHT,,``  

The "ESC" key (which is also the "On" key) is unique in that it has 2 dedicated lines to ASIC2, obviously needed as when the hw is "off" as it's not scanning the whole keyboard.

Of the 18 pins on the main keyboard it's a 9x9 matrix, but pins 1 & 2 are dedicated to "On/ESC" so it's 8x8 for the other 60 keys.

The supplementary case mounted buttons (Task/Del/Home/End/PgUp/PgDn/LCD/Rec) are not covered by this sketch

Teensy LC sketch included here

Further details here: https://zedstarr.com/2022/06/20/repurposing-an-old-psion-mc400-laptop-keyboard-with-teensyduino-usb/

