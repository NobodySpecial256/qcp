# qcp
Inter-VM file copying for Qubes

QCP is a bash script that copies data between qubes. You need to bind it to a keybind in dom0's settings. In my case I use ctrl+F to copy and ctrl+shift+F to paste

Basically, you select whatever files you want to copy. Then you copy them into Qubes' global clipboard with ctrl+shift+C.

Then you copy the files using ctrl+F. It detects what qube is active and keeps track of the source qube for later

You move to the qube you wanna paste into and hit ctrl+shift+F to paste. It detects where to paste the files based on the window title and it sets the user+group of the pasted files to match the originals

It can copy 1 file at a time, or multiple at once

Feel free to review the script for security concerns or submit improvements

### Can I use this to copy files to/from dom0?

No. While it would be simple enough to modify this script to handle dom0's clipboard, copying files to dom0 is a security risk. While copying files from dom0 isn't necessarily as problematic, I thill think it's best simply to avoid dom0 altogether. If you really want to copy files from dom0, use the traditional Qubes method of copying files (`qvm-copy-to-vm`)

### How to copy files to dom0

The Qubes official documentation has information about copying files to dom0: https://www.qubes-os.org/doc/how-to-copy-from-dom0/#copying-to-dom0

For better security, you should download this into a disposable VM, to prevent a compromised qube from tampering with the data locally

For the best security, you should use [qubes-clean](https://github.com/NobodySpecial256/qubes-clean) to copy this script into dom0
