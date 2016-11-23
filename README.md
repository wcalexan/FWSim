# FWSim

To build the envionment for building OpenPower's OCC firmware and the psim PowerPC simulator, I'm using Oracle's VirtualBox with Ubuntu 16.04.

The steps to get the linux environment ready are:

1. Download the ubuntu-15.04-desktop-amd64.iso file (I tried to build using 16.04.1 but it failed the build)
2. From VirtualBox, select New and follow the wizard to create a 12GB disk and point the IDE Secondary Master to the .iso file.  Make sure you allocate at least 2GB of memory for the virtual machine or fcp won't work.
3. Go through the process of the initial Ubuntu installation
  * Choose to download updates as the OS is being installed
  * Choose to Erase Disk and Install Ubuntu
  * Continue writing the changes to the disk
4. Enable the clipboard by going to Settings->General->Advanced->Shared Clipboard = Bidirectional
5. Install Guest Addtions:
  * From a running VM, in the Devices menu, choose **Insert Guest Additions CD image**
  * Follow the prompts
6. Open a terminal (Ctrl-Alt-T)
7. Run the following command to enable focus follows mouse:
  * gsettings set org.gnome.desktop.wm.preferences focus-mode 'sloppy'
8. Install 'git' with:
  * sudo apt install git
9. Clone the open-build git repository:
  * git clone https://github.com/open-power/op-build.git
10. Follow the directions at https://github.com/open-power/op-build under **Building an image**
  * . op-build-env
  * op-build palmetto_defconfig
11. Try putting virtual memory back to 768MB (when it's at 2GB it slows my machine down)
12. Build PSIM by:
  * Download gdb src:  wget http://ftp.gnu.org/gnu/gdb/gdb-7.12.tar.xz
  * xz gdb-7.12.tar.xz
  * tar xvf gdb-7.12.tar
  * cd gdb-7.12
  * export TARGET=powerpc-eabi
  * export PREFIX=/home/wcalexan/psim/bin
  * ./configure --target=$TARGET --prefix=$PREFIX --enable-sim-powerpc --enable-sim-stdio
  * make all
  * make install
  
