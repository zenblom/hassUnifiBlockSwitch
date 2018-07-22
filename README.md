# hassUnifiBlockSwitch
A Home Assitant custom component that allows for block/unblocking a Group on a Ubiquiti Unifi Controller

Summary:
I needed the ability to turn off internet access to a childs devices, they had 4 of them. So I wrote this HASS component to allow me to flip them on or off with a single button (created a group of switched), or I can fine tune and allow select devices on or off if I want. Also allows me to use Automations on the HASS server to turn off internet at specified times, and turn back on automatically. This is my first HASS custom component, feel free to improve.

Install:

1.) Place the file in your hass\custom_components\switch folder. Create the folder if needed.

2.) On your Ubiquiti Controller create a user with read/write permissions (needed to block/unblock users)

3.) Place the devices you want controll over in a group (or use default)

4.) Add to your Hass configuration.yaml:
  
  switch:
    - platform: unifi_client
      verify_ssl: false
      host: "Unifi Controller IP Address"
      username: "UbiquitiUsername"
      password: "UbiquitiPassword"
      port: 8443
      user_group_name: "UbiquitiGroupName"

5.) Restart your Hass server, you should now have "switches" representing each of the devices in the group. Toggling the switch to off will block the device from connecting to the network, toggling the switch on will allow the device to reconnect.
