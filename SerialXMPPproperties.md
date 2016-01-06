# Introduction #

The program looks for the file in the Java app's run directory.  You can edit the SerialXMPP.properties file that is packaged with the app.

Alternatively you can specify an alternative location on the command line using the  -c option

```
java -Djava.library.path=./SerialXMPP_lib/Mac_OS_X/ -classpath .:./SerialXMPP_lib/RXTXcomm.jar:./SerialXMPP_lib/smack.jar:./SerialXMPP_lib/smackx.jar:./XMPPSerialjar_lib/jargs.jar:./ -jar SerialXMPP.jar -c /Users/johnDoe/SomeConfigFileName.properties
```


# Details #
The first 5 option are probably the only one that will need changing if using gmail/gtalk as the XMPP server.  Simply enter the gmail address of the sender and receiver users along with the from users password and thire name of their serial port.



```
fromXMPPaddr=@gmail.com
fromXMPPpassword=
#
toXMPPaddr=@gmail.com
#
serialPort=/dev/tty.usbserial-FTAJLZGV
baud=9600
#
#
#
#
#look for XMPP address  ~[rabbit@example.com] at the begin of the serial stream and send message to this address instead for the default listed in the "toUserid=
#e.g. Arduino
#Serial.println("~[rabbit@example.com]Hi rabbit");  // Sends the message "Hi rabbit" to rabbit@example.com
#NOT IMPLMENTED
useXmppAddrFromMsg=false
#
#
#
XMPPhost=talk.google.com
XMPPport=5222
XMPPserviceName=gmail.com
#
#
#  Status -- free-form text describing a user's presence (i.e., gone to lunch).
Presence.Status=
#  Mode -- one of five presence modes: available (the default), chat, away, xa (extended away), and dnd (do not disturb). 
Presence.Mode=xa
#  Priority -- non-negative numerical priority of a sender's resource. The highest resource priority is the default recipient of packets not addressed to a particular resource.
Presence.Priority=1
#   available -- (Default) indicates the user is available to receive messages.
#   unavailable -- the user is unavailable to receive messages.
Presence.Type=available
```