# Installation

## Install a standard ubuntu 22.04 desktop version

I personally recommend to avoid the graphical system for autodarts. After installation you can switch to a text console using the following command.

`
<STRG>+<ALT>+<F1>
`

## Install additional packages

Adding some packages of which the curl command is the most important. To be honest all others are optional.

`
sudo apt-get install curl guvcview v4l-utils htop openssh-server
`

## Add the current user to the video group to be able to access the cameras

The cameras by default are not readable by everyone. So you need to add the user running autodarts to the group video. You can also replace $USER with your selected user name.

`
sudo addgroup $USER video
`

## Disable the graphical login and an annoying service

Disabling the graphical login as well as an annoying background service which generates too many log entries.

`
sudo systemctl disable snapd.service
sudo systemctl disable snapd.service
sudo systemctl disable gdm.service
`

## Install autodarts

Install autodarts the standard way you already know as usual.

`
bash <(curl -sL get.autodarts.io)
`

## Reboot the system 

After all changes are done reboot before using autodarts. You will not see the cameras if you dont reboot. By the way pressing the start button shuts down the system in seconds.

## Have fun !!!

Yours
nagilo
