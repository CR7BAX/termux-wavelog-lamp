termux-wavelog-lamp
Automated LAMP installer (Apache, MariaDB, PHP 8.2) to run Wavelog inside a Debian container (proot-distro) on Termux, including a watchdog, Adminer and phpSysInfo.

Features
Installs and configures Apache, MariaDB and PHP 8.2 inside Debian (proot-distro) on Termux.​

Downloads and deploys the official Wavelog repository into /var/www/html.

Creates helper scripts to start and stop all services (Apache, MariaDB and watchdog).

Includes menu options to install Adminer (database management) and phpSysInfo (system information).​

Provides a Termux launcher command (wave) to open Debian, run the setup menu and keep the device awake while Wavelog is running.

Requirements
Android device with Termux installed.

proot-distro installed in Termux, with a Debian container already created.

Root shell inside Debian (login as root or use sudo).

Basic Git and wget packages installed inside Debian.​

Installation
Inside Debian (proot-distro):

Clone this repository:

git clone https://github.com/CR7BAX/termux-wavelog-lamp.git

Enter the project directory:

cd termux-wavelog-lamp

Make the installer executable:

chmod +x setup.sh

Run the installer:

./setup.sh

Use the interactive menu to:

Install the LAMP stack.

Create the Wavelog database and user.

Download and configure Wavelog.

Install Adminer and phpSysInfo.

Create the Termux launcher command wave.

Termux launcher (wave)
After creating the launcher from the menu, in a normal Termux session you can simply run:

wave

The launcher:

Acquires a wake-lock so the device does not sleep while the server is running.

Optionally updates the IP helper script (wavelog-ip.sh) if it exists.

Logs into Debian via proot-distro and starts the setup.sh menu.

Releases the wake-lock when you exit the menu.

Accessing Wavelog
After starting Apache, MariaDB and the watchdog from the menu, open a browser (on the phone or another device in the same network) and go to:

http://PHONE_IP:8080

The menu reads the IP from wavelog_ip.txt and prints the correct URL to access Wavelog.

Extras
Adminer: http://PHONE_IP:8080/adminer/

phpSysInfo: http://PHONE_IP:8080/phpsysinfo/​
