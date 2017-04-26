# org.openhab.binding.sharptv

In addition to putting the sharptv jar file into the addons directory, you also may need to put the upnp jar into the addons directory.  If you have another binding installed that uses upnp for discovery, this may not be necessary.

Put the sharptv binding into debug mode so that we can capture what it gets in the upnp response from your TVs.  In the Karaf console you would enter the following.

```
log:set DEBUG org.openhab.binding.sharptv
```

You can open an issue in this repo for any findings/issues your have with the binding, or you can post to the existing thread on the OH2 forum.
