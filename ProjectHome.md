Serial port-->Computer->XMPP/GTALK server-->Computer-->Serial port
bidirectional

This allows for remote serial control


Allows remote serial control/connection to a remote network bypassing firewall by proxying over XMPP. I am working on a Firmata library to complete the loop

You need to control/read a remote serial device , for example, the cat's water bowl connected to an Arduino at your friends house.  There are 2 primary issues with this.
  1. The IP is probably a dynamic one supplied by the cable or phone company
  1. She probably does not want to poke holes in her firewall because she know the mini app has not been thoroughly security checked.

SerialXMPP forwards the incoming Serial stream to an XMPP server and relays all incoming XMPP IM back to that same serial port. all that is needed is a XMPP/Gtalk/Jabber account.

Yes,  This is kinda slow compared to a direct IP connection.  But it meets the above design objectives and I find it generally fast enough for most of my remote control needs.

Gustav von Roth

PLEASE EMAIL ME A LINK TO YOUR PROJECT IF YOU USE THIS.

"gustav AT vonroth c-=-=-o-=-=-=m"