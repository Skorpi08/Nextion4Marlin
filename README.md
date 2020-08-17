must be enabled:

#define PIDTEMP
#define PIDTEMPBED
#define PID_PARAMS_PER_HOTEND 
#define LONG_FILENAME_HOST_SUPPORT
#define EXTENDED_CAPABILITIES_REPORT
#define TEMPERATURE_UNITS_SUPPORT
#define EEPROM_SETTINGS 
#define PRINTCOUNTER
#define SDSUPPORT
#define AUTO_REPORT_SD_STATUS
#define REPRAP_DISCOUNT_FULL_GRAPHIC_SMART_CONTROLLER

Need to change M117.cpp File:

void GcodeSuite::M117() {

  if (parser.string_arg && parser.string_arg[0])
  { ui.set_status(parser.string_arg);

  #if SERIAL_PORT_2 == 2
   MYSERIAL1.print("echo:M117 "); MYSERIAL1.print(parser.string_arg);MYSERIAL1.write(13);
 #endif

  #if SERIAL_PORT == 2
   MYSERIAL0.print("echo:M117 "); MYSERIAL0.print(parser.string_arg);MYSERIAL0.write(13);
 #endif
}
  else
    ui.reset_status();

}
