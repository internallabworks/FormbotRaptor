#ifndef __AVR_ATmega2560__
  #error "Oops!  Make sure you have 'Arduino Mega' selected from the 'Tools -> Boards' menu."
#endif

#if E_STEPPERS > 3 || HOTENDS > 3
  #error "Formbot supports up to 3 hotends / E-steppers. Comment this line to keep going."
#endif

#define DEFAULT_MACHINE_NAME "Formbot"
#define BOARD_NAME           "Formbot"

//
// Servos
//
#define SERVO0_PIN         ar11
#define SERVO1_PIN          ar6
#define SERVO2_PIN          ar5
#define SERVO3_PIN         -1

//
// Limit Switches
//
#define X_MIN_PIN          ar3
#define X_MAX_PIN          ar2
#define Y_MIN_PIN          ar14
#define Y_MAX_PIN          ar15
#define Z_MIN_PIN          ar18
#define Z_MAX_PIN          ar19

//
// Z Probe (when not Z_MIN_PIN)
//
#ifndef Z_MIN_PROBE_PIN
  #define Z_MIN_PROBE_PIN  ar32
#endif

//
// Steppers
//
#define X_STEP_PIN         ar54
#define X_DIR_PIN          ar55
#define X_ENABLE_PIN       ar38
#ifndef X_CS_PIN
  #define X_CS_PIN         ar53
#endif

#define Y_STEP_PIN         ar60
#define Y_DIR_PIN          ar61
#define Y_ENABLE_PIN       ar56
#ifndef Y_CS_PIN
  #define Y_CS_PIN         ar49
#endif

#define Z_STEP_PIN         ar46
#define Z_DIR_PIN          ar48
#define Z_ENABLE_PIN       ar62
#ifndef Z_CS_PIN
  #define Z_CS_PIN         ar40
#endif

#define E0_STEP_PIN        ar26
#define E0_DIR_PIN         ar28
#define E0_ENABLE_PIN      ar24
#ifndef E0_CS_PIN
  #define E0_CS_PIN        ar42
#endif

#define E1_STEP_PIN        ar36
#define E1_DIR_PIN         ar34
#define E1_ENABLE_PIN      ar30
#ifndef E1_CS_PIN
  #define E1_CS_PIN        ar44
#endif

#define E2_STEP_PIN        ar42
#define E2_DIR_PIN         ar43
#define E2_ENABLE_PIN      ar44

//
// Temperature Sensors
//
#define TEMP_0_PIN         analog13   // Analog Input
#define TEMP_1_PIN         analog15   // Analog Input
#define TEMP_BED_PIN        analog3   // Analog Input

// SPI for Max6675 or Max31855 Thermocouple
#if DISABLED(SDSUPPORT)
  #define MAX6675_SS       ar66 // Do not use pin 53 if there is even the remote possibility of using Display/SD card
#else
  #define MAX6675_SS       ar66 // Do not use pin 49 as this is tied to the switch inside the SD card socket to detect if there is an SD card present
#endif


//
// Heaters / Fans
//
#define HEATER_0_PIN       ar10
#define HEATER_1_PIN        ar7
#define HEATER_BED_PIN     ar58

#define LED4_PIN            ar8

#define FAN_PIN             ar9

#if DISABLED(FILAMENT_RUNOUT_SENSOR)
  #define FAN1_PIN          ar4
#endif

//
// Misc. Functions
//
#define SDSS               ar53
#ifndef ROXYs_TRex
  #define LED_PIN          ar13
#endi

// Use the RAMPS 1.4 Analog input 5 on the AUX2 connector
#define FILWIDTH_PIN        analog5   // Analog Input

#ifndef PS_ON_PIN
  #define PS_ON_PIN        ar12
#endif

//
// LCD / Controller
//
// Formbot only supports REPRAP_DISCOUNT_SMART_CONTROLLER
//
#if ENABLED(REPRAP_DISCOUNT_SMART_CONTROLLER)
  #define LCD_PINS_RS      ar16
  #define LCD_PINS_ENABLE  ar17
  #define LCD_PINS_D4      ar23
  #define LCD_PINS_D5      ar25
  #define LCD_PINS_D6      ar27
  #define LCD_PINS_D7      ar29
  #define BTN_EN1          ar31
  #define BTN_EN2          ar33
  #define BTN_ENC          ar35
  #define SD_DETECT_PIN    ar49
  #ifndef ROXYs_TRex
    #define KILL_PIN       ar41
    #define BEEPER_PIN     ar37
  #endif
#endif