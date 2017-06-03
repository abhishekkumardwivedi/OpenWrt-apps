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

