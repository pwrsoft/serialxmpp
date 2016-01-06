# Command line options #
It the main start up directory there is a file called SerialXMPP.properties .  This file has all the configuration information.  IF command line options are use they superceed what is written this properties file.  If you wish to specify a different location for the properties file this can be done with the -c command line argument.


  * -f  The fromXMPPaddr
  * -p  The fromXMPPpassword
  * -t  The toXMPPaddr
  * -s  The serialPortPram
  * -c  The properties file (should be pick up automatically if apps started from the same dir)

# Start-up #
There are sample start up files for Mac, Linux, and Windows in shell and batch format.

command line option go at the end of the example command lines