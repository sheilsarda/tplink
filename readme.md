## TP-Link HS100 Web Client

### Why?

TP-Link give you access to your HS-100 range devices through the KASA app on IOS / Android. That's fine, but what if you're
in front of your desktop / tablet / etc, and don't have your phone to hand? How annoying to have to fish it out of your pocket
just to flick a switch. 

This angular material web-page provides the service TP-Link omitted. You can log into the TP-Link API to generate a service token,
have it look up the devices stored against your account, monitor and set their power state. 

If you've just added TP-Link devices to a smart home network and want to be able to control them all from one place, you can 
examine the source of this project and utilise the calls within your own pages. Or just use this one :)


### Features:

 - generates a UUID
 - capture credentials.
 - authenticates against the tp-link api service to get a secure authentication token
 - uses that token to:
  - list the devices stored against your account
  - send on/off commands to them.
  - reflect whether the devices are currently on or not.
 - optionally stores the token (and/or credentials) so that you can jump straight to it next time.
 
 
### Notes:

If you opt to store your token or credentials, these are held in a browser cookie on *your* machine. In use, they are sent directly from your
browser to the TP-Link API endpoint via https, and are not sent to any other web host.

#### Sample `response_data`

````json
responseData: "{\"system\":{\"get_sysinfo\":{\"sw_ver\":\"1.0.18 Build 210910 Rel.141202\",\"hw_ver\":\"1.0\",\"model\":\"KP115(US)\",\"deviceId\":\"8006A1CC73ECF70CE0589933D308D8701DE08775\",\"oemId\":\"9FDE0C9E37EDF4495F681216FEFB0CFB\",\"hwId\":\"3E2B9A976B98DCFC5C83D11C8CEF7510\",\"rssi\":-55,\"latitude_i\":400134,\"longitude_i\":-752347,\"alias\":\"sheil\",\"status\":\"configured\",\"obd_src\":\"tplink\",\"mic_type\":\"IOT.SMARTPLUGSWITCH\",\"feature\":\"TIM:ENE\",\"mac\":\"C0:C9:E3:0E:42:39\",\"updating\":0,\"led_off\":0,\"relay_state\":1,\"on_time\":38982,\"icon_hash\":\"\",\"dev_name\":\"Smart Wi-Fi Plug Mini\",\"active_mode\":\"none\",\"next_action\":{\"type\":-1},\"ntc_state\":0,\"err_code\":0}},\"emeter\":{\"get_realtime\":{\"current_ma\":88,\"voltage_mv\":123566,\"power_mw\":8903,\"total_wh\":139,\"err_code\":0}}}"
````