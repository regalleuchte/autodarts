# Installation

1. Install a standard ubuntu 22.04 desktop version

I personally recommend to avoid the graphical system for autodarts. You can switch to a text console using the command 

`
<STRG>+<ALT>+<F1>
`

2. Install additional packages
`
sudo apt-get install curl guvcview v4l-utils htop openssh-server
`

3. Add the current user to the video group to be able to access the cameras

`
sudo addgroup user video
`

4. Disable the graphical login and an annoying service

`
sudo systemctl disable snapd.service
sudo systemctl disable snapd.service
sudo systemctl disable gdm.service
`

5. Install autodarts

`
bash <(curl -sL get.autodarts.io)
`
