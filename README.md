# org.openhab.binding.sharptv

In addition to putting the sharptv jar file into the addons directory, you also may need to put the upnp jar into the addons directory.  If you have another binding installed that uses upnp for discovery, this may not be necessary.

Put the sharptv binding into debug mode so that we can capture what it gets in the upnp response from your TVs.  In the Karaf console you would enter the following.

```
log:set DEBUG org.openhab.binding.sharptv
```

You can open an issue in this repo for any findings/issues your have with the binding, or you can post to the existing thread on the OH2 forum.

Here are the items I was using for testing:

```
Switch SharpTV_Power        "Power [%s]"            { channel="sharptv:sharptv:f8b7a5c8-7917-11e5-80a3-242642edb3b3:power" }
Dimmer SharpTV_Volume       "Volume [%.0f %%]"      { channel="sharptv:sharptv:f8b7a5c8-7917-11e5-80a3-242642edb3b3:volume" }
Switch SharpTV_Mute         "Mute [%s]"             { channel="sharptv:sharptv:f8b7a5c8-7917-11e5-80a3-242642edb3b3:mute" }
Dimmer SharpTV_Channel      "Channel [%.0f]"        { channel="sharptv:sharptv:f8b7a5c8-7917-11e5-80a3-242642edb3b3:channel" }
Number SharpTV_Input        "Input [%.0f]"          { channel="sharptv:sharptv:f8b7a5c8-7917-11e5-80a3-242642edb3b3:input" }
Number SharpTV_AvMode       "AV Mode [%.0f]"        { channel="sharptv:sharptv:f8b7a5c8-7917-11e5-80a3-242642edb3b3:av-mode" }
Switch SharpTV_DisableEco   "DisableEco Mode"       { channel="sharptv:sharptv:f8b7a5c8-7917-11e5-80a3-242642edb3b3:disable-eco" }
```

For powering on or off, send that item the ON or OFF commands.

For setting volume, you can set the item to a value between 0 and 100, or send that item the INCREASE or DECREASE command.

For muting/unmuting, send that item the On or OFF commands.

For setting the channel, you can set the item to the value of the channel, or send that item the INCREASE or DECREASE command.

For selecting input, you set the item to 1 for HDMI1, 2 for HDMI2, etc.

For setting the AV Mode, you set the item to the number that corresponds to the desired AV Mode.  There doesn't appear to be a standard numbering scheme, so you may need to consult the manual for your specific model TV.

Sending a ON or OFF command to the disable-eco channel will cause the binding to send the `RSPW2` command to the TV.
