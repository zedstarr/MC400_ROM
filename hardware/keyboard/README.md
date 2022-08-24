Keyboard matrix decoded with the help of Frank Adams' Teensyduino sketch from https://github.com/thedalles77/USB_Laptop_Keyboard_Controller

In Action:

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/tcAmia2SWaY/0.jpg)](https://www.youtube.com/watch?v=tcAmia2SWaY)

https://youtube.com/shorts/tcAmia2SWaY?feature=share

![MC400 keyboard matrix](https://github.com/zedstarr/MC400_ROM/raw/main/hardware/keyboard/Screenshot%20from%202022-08-23%2015-29-46.png)

Matrix available in the .ino code or in the .xlsx file ;-) 

```
int normal[rows_max][cols_max] = {
{KEY_ESC,0,0,0,0,0,0,0,0},
{0,0,KEY_1,KEY_3,KEY_5,KEY_7,KEY_9,KEY_MINUS,KEY_BACKSPACE},
{0,0,KEY_2,KEY_4,KEY_6,KEY_8,KEY_0,KEY_EQUAL,KEY_TAB},
{0,0,KEY_Q,KEY_E,KEY_T,KEY_U,KEY_O,KEY_LEFT_BRACE,0},
{0,KEY_CAPS_LOCK,KEY_W,KEY_R,KEY_Y,KEY_I,KEY_P,KEY_RIGHT_BRACE,KEY_BACKSLASH},
{0,0,KEY_A,KEY_D,KEY_G,KEY_J,KEY_L,KEY_QUOTE,0},
{0,0,KEY_S,KEY_F,KEY_H,KEY_K,KEY_SEMICOLON,KEY_TILDE,0},
{0,KEY_LEFT,KEY_Z,KEY_C,KEY_B,KEY_M,KEY_PERIOD,KEY_UP,KEY_SPACE},
{0,KEY_DOWN,KEY_X,KEY_V,KEY_N,KEY_COMMA,KEY_SLASH,KEY_ENTER,KEY_RIGHT},
};
// Load the modifier key matrix with key names at the correct row-column location. 
// A zero indicates no modifier key at that location.
int modifier[rows_max][cols_max] = {
{0,0,0,0,0,0,0,0,0},
{0,MODIFIERKEY_CTRL,0,0,0,0,0,0,0},
{0,MODIFIERKEY_SHIFT,0,0,0,0,0,0,0},
{0,MODIFIERKEY_ALT,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
{0,MODIFIERKEY_RIGHT_SHIFT,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
};
// Load the media key matrix with Fn key names at the correct row-column location. 
// A zero indicates no media key at that location.
int media[rows_max][cols_max] = {
{0,0,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0,0},
};
```

The "ESC" key (which is also the "On" key) is unique in that it has 2 dedicated lines to ASIC2, obviously needed as when the hw is "off" as it's not scanning the whole keyboard.

Of the 18 pins on the main keyboard it's a 9x9 matrix, but pins 1 & 2 are dedicated to "On/ESC" so it's 8x8 for the other 60 keys.

The supplementary case mounted buttons (Task/Del/Home/End/PgUp/PgDn/LCD/Rec) are not covered by this sketch

Teensy LC sketch included here

Further details here: https://zedstarr.com/2022/06/20/repurposing-an-old-psion-mc400-laptop-keyboard-with-teensyduino-usb/

