# ha_huawei_solar_replicate
Replica power sensor, read source, from target to show on target Home Assistant instance.

Testet on:
HAOS = 11.4 # HAC = 2024.1.3

And:
HAOS = 11.5 # HAC = 2024.2.1

# !!! Always make sure to back up everything before you begin !!!


# On source HA: #

 Ensure the following:

 The correct IP address of your source Home Assistant instance.

 Replace "YOUR_LONG_LIVED_ACCESS_TOKEN" from source HA, with your actual long-lived access token from the source.


# You’ll find this token-menu when you click your username on the lower left corner in HA. #

Token Name: huawei solar replicate

This is an example Token that is used in the example below, remember to insert youre own to all sensors.

Use the "search" and replace in HA file editor, here are what to search for.

Source IP: 192.168.10.24

Source Token: YOUR_LONG_LIVED_ACCESS_TOKEN

Once you've verified these details and insert youre IP and Token to the huawei_solar_replicate_target.yaml, this setup should work as intended.


# On target HA: 

In "configuration.yaml" add:

    homeassistant:


        huawei_solar_replicate: !include packages/huawei_solar_replicate_target.yaml

Copy this file "huawei_solar_replicate_target.yaml" to target HA "packages" folder

packages/huawei_solar_replicate_target.yaml

Then Restart HA
