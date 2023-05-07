# Kernel Module

## cap

The capability based kernel module allows the setting of specfic bandwidth according to 

https://www.thegoodpenguin.co.uk/blog/multiple-uvc-cameras-on-linux/

Use the following command to set about 153.6 Mbps = ( (2400*8000*8) / 1000000).

echo 2400 > /sys/module/uvcvideo/parameters/bandwidth_cap

## hack

The kernel module sets the bandwidth to a predefined fixed value

## usage

Replace the following file with one of the versions mentioned above

/lib/modules/5.10.0-18-amd64/kernel/drivers/media/usb/uvc/uvcvideo.ko

