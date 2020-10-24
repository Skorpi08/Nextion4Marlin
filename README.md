
<h1 style="color: #5e9ca0;">If you are missing any features, please let me know.
This Version works only with Intelligent Series.</h1>

<h2 style="color: #2e6c80;">Must be enabled:</h2>
<ol style="list-style: none; font-size: 14px; line-height: 32px; font-weight: bold;">
<li style="clear: both;">#define PIDTEMP<br />#define PIDTEMPBED<br />#define PID_PARAMS_PER_HOTEND <br />#define LONG_FILENAME_HOST_SUPPORT<br />#define EXTENDED_CAPABILITIES_REPORT<br />#define TEMPERATURE_UNITS_SUPPORT<br />#define EEPROM_SETTINGS <br />#define PRINTCOUNTER<br />#define SDSUPPORT<br />#define AUTO_REPORT_SD_STATUS<br />#define REPRAP_DISCOUNT_FULL_GRAPHIC_SMART_CONTROLLER<br />#define DISTINCT_E_FACTORS</li>
</ol>
<p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</p>
<h2 style="color: #2e6c80;">&nbsp;change M117.cpp File:</h2>
<ol style="list-style: none; font-size: 14px; line-height: 32px; font-weight: bold;">
<li style="clear: both;">
<p>void GcodeSuite::M117() {</p>
<p>if (parser.string_arg &amp;&amp; parser.string_arg[0])<br /> { ui.set_status(parser.string_arg);</p>
<p>#if SERIAL_PORT_2 == 2<br /> MYSERIAL1.print("echo:M117 "); MYSERIAL1.print(parser.string_arg);MYSERIAL1.write(13);<br /> #endif</p>
<p>#if SERIAL_PORT == 2<br /> MYSERIAL0.print("echo:M117 "); MYSERIAL0.print(parser.string_arg);MYSERIAL0.write(13);<br /> #endif<br />}<br /> else<br /> ui.reset_status();</p>
<p>}</p>
</li>
</ol>
<p>&nbsp;</p>
<p><strong>&nbsp;</strong></p>
<p>&nbsp;</p>
