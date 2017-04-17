# things
Starting Vivado
===============

We just installed Vivado. Now we’re going to run it for the first time.

Open a terminal and source this file source /opt/Xilinx/Vivado/2015.1/settings64.sh. Add it to your ~/.bashrc file so it’s run each time you launch a terminal.

Make a directory for projects and launch vivado. The whole sequence is below.

    source /opt/Xilinx/Vivado/2015.1/settings64.sh
    mkdir ~/vivado
    cd ~/vivado
    vivado &

Unfortunately, I had some errors at first start-up. The following commands helped.

    sudo chmod 777 -R /opt/Xilinx/
    sudo chmod 777 -R ~/.Xilinx/

Try again.

    vivado &

Vivado starts up and we’re ready to program!


to do apt-get faster
====================

Add -o Acquire::ForceIPv4=true when running apt-get.

If you want to make the setting persistent just create /etc/apt/apt.conf.d/99force-ipv4 and put Acquire::ForceIPv4 "true"; in it:

    echo 'Acquire::ForceIPv4 "true";' | sudo tee /etc/apt/apt.conf.d/99force-ipv4

Config options Acquire::ForceIPv4 and Acquire::ForceIPv6 were added to version 0.9.7.9~exp1 (see bug 611891) which is available since Ubuntu Saucy (released in October 2013) and Debian Jessie (released in April 2015).


Get wifi working
================

A better solution is to install the driver using DKMS. This way you won't need to re-install it
after kernel uprades. Do it this way:

    sudo apt-get install git dkms build-essential
    git clone https://github.com/neurobin/MT7630E.git
    cd MT7630E/
    sudo make dkms


git things
==========

1. change
2. terminal
    git add .
    git commit -m "message"
    git push origin branch

