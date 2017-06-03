# OpenWrt-apps
## Packages
`
//video streaming
opkg install kmod-video-uvc mjpg-streamer
`

Enable mjpg-streamer by setting enable '1'

`
vi /etc/config/mjpg-streamer
`
`
config mjpg-streamer 'core'
        option enabled '1'
        option input 'uvc'
        option output 'http'
        option device '/dev/video0'
        option resolution '640x480'
        option yuv '0'
        option quality '80'
        option fps '5'
        option led 'auto'
        option www '/www/webcam'
        option port '8080'
        option username 'openwrt'
        option password 'openwrt'
`

Now, start streaming by:
`
/etc/init.d/mjpg-streamer start
`
We can see any indicator, led, in camera turned on.

To stop streaming:
`
/etc/init.d/mjpg-streamer stop
`

## USB over IP tunnel
`
opkg install http://downloads.lede-project.org/releases/17.01.1/targets/ramips/mt7688/packages/kmod-usbip-client_4.4.61-1_mipsel_24kc.ipk

opkg install http://downloads.lede-project.org/releases/17.01.1/targets/ramips/mt7688/packages/kmod-usbip-server_4.4.61-1_mipsel_24kc.ipk

opkg install http://downloads.lede-project.org/releases/17.01.1/targets/ramips/mt7688/packages/kmod-usbip_4.4.61-1_mipsel_24kc.ipk
`

## Debugging utils
`
opkg print-architecture
uname -a
`
## Reference

* https://downloads.lede-project.org/releases/17.01.1/targets/ramips/mt7688/packages/
