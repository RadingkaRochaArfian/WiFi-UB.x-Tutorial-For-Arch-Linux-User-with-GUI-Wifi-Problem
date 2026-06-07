# How to Connect to WiFi-UB-x on Arch Linux
*For educational and reference purpose*
## Step 1: Connecting
>Connect to WiFi-UB-x with NIM as your Username and UB account password as the wifi password
>
>It should ask you password again
>
>Close the window that ask your password
>
>Do not delete the wifi

## Step 2: Configuring
>Open your terminal
>
>Run: sudo nano /etc/NetworkManager/system-connections/WiFi-UB.x.nmconnection

It is more or less like this

```
[connection]
id=WiFi-UB.x
uuid=.....
type=wifi
interface-name=wlan0
permissions=user:....:;

[wifi]
mode=infrastructure
ssid=WiFi-UB.x

[wifi-security]
auth-alg=open
key-mgmt=wpa-eap

[802-1x]
eap=peap;
identity=255150200
password-flags=1
phase2-auth=mschapv2
[ipv4]
method=auto

[ipv6]
addr-gen-mode=stable-privacy
method=auto

[proxy]
 ```
>Add below "[802-1x]": phase1-auth-flags=32

It is more or less like this

```
[connection]
id=WiFi-UB.x
uuid=.....
type=wifi
interface-name=wlan0
permissions=user:....:;

[wifi]
mode=infrastructure
ssid=WiFi-UB.x

[wifi-security]
auth-alg=open
key-mgmt=wpa-eap

[802-1x]
eap=peap;
identity=255150200
password-flags=1
phase2-auth=mschapv2
phase1-auth-flags=32
[ipv4]
method=auto

[ipv6]
addr-gen-mode=stable-privacy
method=auto

[proxy]
 ```  
>Save and leave nano: Ctrl+o (save) click enter then Ctrl+x (Exit)

## Step 3: Reconnecting

>Try to reconnect back to wifi and it should connect your device to WiFi-UB.x
