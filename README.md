# ha_huawei_solar_replicate
Replica power sensor, read source, from target to show on target Home Assistant instance.

![Skærmbillede fra 2024-02-10 12-33-54](https://github.com/JacobsenKim/ha_huawei_solar_replicate/assets/157890151/cbc473f8-fd0c-4306-93cc-7a933ac2f6b0)


![Skærmbillede fra 2024-02-10 13-59-57](https://github.com/JacobsenKim/ha_huawei_solar_replicate/assets/157890151/6e724672-a1ef-4ccc-bccf-c957d651e05e)


![Skærmbillede fra 2024-02-10 12-34-21](https://github.com/JacobsenKim/ha_huawei_solar_replicate/assets/157890151/32234a3d-454a-4337-b7ae-06ccbccbd9df)


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

Create new Token

Token Name: huawei solar replicate


# On target HA: 

Copy this file "huawei_solar_replicate_target.yaml" to target Home Assistant instance "packages" folder, if you dont have "packages" folder one need to create "packages" folder.

Then open packages/huawei_solar_replicate_target.yaml

# Use the "search" and replace in HA file editor, here are what to search for.

Source IP: 192.168.10.24

Source Token: YOUR_LONG_LIVED_ACCESS_TOKEN

Once you've verified these details and insert youre IP and Token to huawei_solar_replicate_target.yaml, this setup should work as intended.


In "configuration.yaml" add:

    homeassistant:
#

        huawei_solar_replicate: !include packages/huawei_solar_replicate_target.yaml


Then Restart Home Assistant.
