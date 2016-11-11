# FWSim

To build the envionment for building OpenPower's OCC firmware and the psim PowerPC simulator, I'm using Oracle's VirtualBox with Ubuntu 16.04.

The steps to get the linux environment ready are:

1. Download the ubuntu-16.04.1-desktop-amd64.iso file.
2. From VirtualBox, select New and follow the wizard to create a 12GB disk and point the IDE Secondary Master to the .iso file.
3. Go through the process of the initial Ubuntu installation
  * Choose to download updates as the OS is being installed
  * Choose to Erase Disk and Install Ubuntu
  * Continue writing the changes to the disk
4. Enable the clipboard by going to Settings->General->Advanced->Shared Clipboard = Bidirectional
5. Open a terminal (Ctrl-Alt-T)
6. Run the following command to enable focus follows mouse:
    gsettings set org.gnome.desktop.wm.preferences focus-mode 'sloppy'
7. 
