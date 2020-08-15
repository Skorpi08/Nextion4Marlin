Need to change M117.cpp File:

void GcodeSuite::M117() {

  if (parser.string_arg && parser.string_arg[0])
  { ui.set_status(parser.string_arg);
  
    MYSERIAL0.print("echo:M117 "); MYSERIAL0.print(parser.string_arg);MYSERIAL0.write(13);
      
  }
  else
    ui.reset_status();

}
