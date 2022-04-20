# Softether Auto Install Multi Platform<br />
* Softether Auto Install Script for multi platforms updated version<br />
* Softether VPN server latest version v4.27-9666-beta-2018.04.21
* Revised to last known stable version due to compilation error from their latest release
* An open source VPN project from University of Tsukuba Japan<br />
* Centos 6 or 7 x64
* Debian 8 (jessie) <b>(Not compatible for Debian 9 (stretch) x64 - compilation error)</b>
* Ubuntu 14, 15, 16 x64 <b>(Not compatible for Ubuntu 17 and 18 x64 - compilation error)</b>
# Instruction<br />
Choose your desired platform folder<br />
Download installer.sh using wget or transfer to your root directory using ftp<br /><br />

<b>Download and install the installer.sh by executing the commands below</b><br /><br />
<b>For centos and fedora</b> (copy all the text below and paste on your terminal)<br /><br />
```yum install wget -y && wget https://raw.githubusercontent.com/jaysonvelagio/SoftetherAutoInstallMultiPlatform/master/Centos/installer.sh && chmod +x installer.sh && ./installer.sh ```<br /><br /><br />


<b>For debian and ubuntu</b> (copy all the text below and paste on your terminal)<br /><br />
```wget #--------------------------------------------------
#Softether auto install script
#Debian and Ubuntu
#Created May 25, 2018
#Latest Softether Server Version for May 2018 v4.27-9667-beta-2018.05.26-tree
#Coded by Jayson Velagio
#Open Source Project From https://www.softether.org/
#From university of Tsukuba, Japan
#--------------------------------------------------
#Login with root permission or execute #sudo su
#Script start
#--------------------------------------------------
#Updating centos version
cd /root
apt-get update -y
apt-get install build-essential -y
#Downloading server files
wget http://www.softether-download.com/files/softether/v4.38-9760-rtm-2021.08.17-tree/Linux/SoftEther_VPN_Server/64bit_-_Intel_x64_or_AMD64/softether-vpnserver-v4.38-9760-rtm-2021.08.17-linux-x64-64bit.tar.gz
tar zxf softether-vpnserver-v4.38-9760-rtm-2021.08.17-linux-x64-64bit.tar.gz
cd vpnserver
#Installing server files, Manual input
clear
echo  -e "\033[31;7mNOTE: ANSWER 1 AND ENTER THREE TIMES FOR THE COMPILATION TO PROCEED\033[0m"
make
cd /root
mv vpnserver /usr/local
rm -rf softether-vpnserver-v4.38-9760-rtm-2021.08.17-linux-x64-64bit.tar.gz
cd /usr/local/vpnserver
chmod 600 *
chmod 700 vpncmd
chmod 700 vpnserver
#Installing server command
wget https://raw.githubusercontent.com/psytisfaction/sftether/master/Debian%20and%20Ubuntu/vpn-server.sh --no-check-certificate
mv vpn-server.sh /etc/init.d/vpnserver
cd /etc/init.d/
chmod 755 vpnserver
update-rc.d vpnserver defaults
/etc/init.d/vpnserver start
cd /usr/local/vpnserver
echo ---------------------------------------------
echo  -e "\033[32;5mVPN SERVER INSTALLED SUCCESSFULLY!\033[0m"
echo "SoftEther auto installer by JAYSON VELAGIO"
echo "vpncmd is at /usr/local/vpnserver"
echo ---------------Commands----------------------
echo /etc/init.d/vpnserver start - to start
echo /etc/init.d/vpnserver restart - to restart
echo /etc/init.d/vpnserver stop - to stop
echo ---------------------------------------------
#End of script
 && chmod +x installer.sh && ./installer.sh```<br /><br /><br />


# VPN server commands<br />
```/etc/init.d/vpnserver start - to start```<br />
```/etc/init.d/vpnserver restart - to restart```<br />
```/etc/init.d/vpnserver stop - to stop```<br /><br />

* vpncmd is at /usr/local/vpnserver<br /><br />

If you can't connect to your vpn server using VPN server manager. Open this ports on your firewall dashboard if you are using Google cloud, Amazon AWS, Alibaba Cloud and Digital Ocean<br />

TCP 443<br />
TCP 992<br />
TCP 1194<br />
TCP 5555<br />


For more information message me on facebook: Jayson Velagio
