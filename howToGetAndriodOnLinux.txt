#The Linux machine will need to be running the GNOME desktop environment. You'll also need to install the KDE Connect app on your Android device (found on the Google Play Store).

#Checking if the shell extension support is working by typing
sudo dnf install chrome-gnome-shell

#With your browser go the to GSConnect Gnome shell extension page and you should see a slider that can be turned on or off. turn it on to download the extension in gnome shell.
https://extensions.gnome.org/extension/1319/gsconnect/

#After sucessfull installation you should see a new system tray option called mobile devices. CLick that and go to mobile settting and you should see your mobile device listted.
#If you run into problems make sure port numbers 1716 through 1764 are open for both the TCP and UDP protocols by running this command.
sudo iptables -I INPUT -p tcp --dport 1714:1764 -j ACCEPT
sudo iptables -I INPUT -p udp --dport 1714:1764 -j ACCEPT

#Also ping your phone to see if it can be reached using the ping command.
ping (your phones ip address)

#If that does not work stop your firewall briefly and check if you phone and/or GSConnect has detected each other and pair the devices. Finally restart your firewall.
sudo systemctl stop firewalld.service
sudo systemctl start firewall.service

#Links to websites with step by step instructions that I  used for help. The above where problems I ran into myself and ways I solved my issues.
https://www.techrepublic.com/article/how-to-connect-your-android-device-to-your-linux-desktop/
https://extensions.gnome.org/extension/1319/gsconnect/
https://darshpreets.wordpress.com/2019/06/27/kde-connect-not-showing-any-devices-solution/
https://forum.kde.org/viewtopic.php?t=139460

#project complete
