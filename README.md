# qcp
Inter-VM file copying for Qubes

QCP is a bash script that copies data between qubes. You need to bind it to a keybind in dom0's settings. In my case I use ctrl+F to copy and ctrl+shift+F to paste

Basically, you select whatever files you want to copy. Then you copy them into Qubes' global clipboard with ctrl+shift+C.

Then you copy the files using ctrl+F. It detects what qube is active and keeps track of the source qube for later

You move to the qube you wanna paste into and hit ctrl+shift+F to paste. It detects where to paste the files based on the window title and it sets the user+group of the pasted files to match the originals

It can copy 1 file at a time, or multiple at once

Feel free to review the script for security concerns or submit improvements
