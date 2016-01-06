# Introduction #

On Mac the "smack" library (This is the XMPP interface library) generates a keystore error.  This will not effect operation but it is ugly. If it really bothers you  follow the below directions.


# Details #

```
Intro

In the latest (Dec 2009) update of Java for Mac Snow Leopard, Apple decided to change the default password of the CA certificate key store from "changeit" to "changeme". This creates a problem while connecting with the smack lib (XMPP/Jabber) to the server.
Exception

javava.io.IOException: Keystore was tampered with, or password was incorrect
    at sun.security.provider.JavaKeyStore.engineLoad(JavaKeyStore.java:771)
    at sun.security.provider.JavaKeyStore$JKS.engineLoad(JavaKeyStore.java:38)
    at java.security.KeyStore.load(KeyStore.java:1185)
    at org.jivesoftware.smack.ServerTrustManager.<init>(ServerTrustManager.java:63)
    at org.jivesoftware.smack.XMPPConnection.proceedTLSReceived(XMPPConnection.java:1246)
    at org.jivesoftware.smack.PacketReader.parsePackets(PacketReader.java:313)
    at org.jivesoftware.smack.PacketReader.access$000(PacketReader.java:44)
    at org.jivesoftware.smack.PacketReader$1.run(PacketReader.java:76)
Caused by: java.security.UnrecoverableKeyException: Password verification failed
    at sun.security.provider.JavaKeyStore.engineLoad(JavaKeyStore.java:769)
    ... 7 more
Solution

   1. Go to /System/Library/Frameworks/JavaVM.framework/Resources/Deploy.bundle/Contents/Home/lib/security/
   2. Change to root with sudo su
   3. Type in your <password>
   4. Then as root do the following
   5. keytool -storepasswd -keystore cacerts (with this command you will change the password for the CA certificate file)
   6. Current password: changeme
   7. Set it to: changeit (default password from sun on all systems but apple) (type it twice)
   8. Finally enjoy smack without exceptions on the mac...
```