# Sound production linux resources and tips

## My configuration

Hardware
- Allen&Heath ZED10FX
- Focusrite Scarlett 2i2

Software
- Kubunutu 20.10
- `pulseaudio` server

## Day-to-day usage commands

All usage to control a running PulseAudio sound server could be done with:
```bash
pactl --help
pactl [options] stat
pactl [options] info
pactl [options] list [short] [TYPE]
pactl [options] load-module  NAME [ARGS ...]
pactl [options] unload-module  NAME
``` 

---

Master properly every INPUT / OUTPUT with the volume control panel for the PulseAudio sound server.
```bash
pavucontrol
pavucontrol &
```

---

Use the module loopback to initiate every possible loopback from INPUT to OUTPUT.
```bash
pactl load-module module-loopback
```

---

Kill PulseAudio and **remove all its configuration**. *Use this command carefully.* \
Use this command when you fucked up your audio routing and want a fresh start!

```bash
killall pulseaudio; rm -r ~/.config/pulse/*
```

## Recording

You can easily record a PulseAudio server with Audacity. \
```bash
audacity
audacity &
```

Set-up Audacity to use `pulse` as input .. and voilà! \
You can directly listen the recorded source use a loopback. 
