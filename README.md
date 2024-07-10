# PiRFtoIR

These are notes for allowing an RF device (in this case a projector screen) to be controlled by an IR remote (such as Harmony remote) by using a Raspberry Pi as an intermediary.

--------------------------------------------------------
/home/pi/.bashrc
--------------------------------------------------------
Very last lines set the Page Up and Page Down keys to run appropriate scripts for the projector screen (the code is found by pressing Ctrl-V on the keyboard and then pressing the corresponding key).

echo Setting up PgDwn/PgUp for projector
bind '"\e[6~":"/home/pi/projector_down.sh\n"'
bind '"\e[5~":"/home/pi/projector_up.sh\n"'

--------------------------------------------------------
RF CODES
--------------------------------------------------------
All RF tools are in ~/433utils/RPi_utils.
./RFSniffer - will show a numeral representation of a received code
./codesend [number] - will transmit the given [number]

--------------------------------------------------------
IR CODES
--------------------------------------------------------
flirc_util is installed to help transmit IR commands, but this isn't done yet.

--------------------------------------------------------
/home/pi/projector_down.sh
--------------------------------------------------------
~/433utils/RPi_utils/codesend 8059332
~/433utils/RPi_utils/codesend 8059332
~/433utils/RPi_utils/codesend 8059332
sleep 5
~/433utils/RPi_utils/codesend 8059332
~/433utils/RPi_utils/codesend 8059332
~/433utils/RPi_utils/codesend 8059332

--------------------------------------------------------
/home/pi/projector_up.sh
--------------------------------------------------------
~/433utils/RPi_utils/codesend 8059329
~/433utils/RPi_utils/codesend 8059329
~/433utils/RPi_utils/codesend 8059329
sleep 5
~/433utils/RPi_utils/codesend 8059329
~/433utils/RPi_utils/codesend 8059329
~/433utils/RPi_utils/codesend 8059329
