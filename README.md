# linux_mint_18.3_and_bluetooth_headphone
Solution for connecting bluetooth headphone "Bose QC35 II" with LinuxMint 18.3.

In case your `/var/log/syslog` shows
```
a2dp-sink profile connect failed for BLUETOOTH:DEVICE:ID: Protocol not available
```

Then the installation of the pulseaudio bluetooth library is necessary, therefore the script
`install_prerequisites.sh` is provided, pulseaudio is also needed, but not included in the script,
because chances are high that it is already in place...

Restart your operating system, so that the pulseaudio bluetooth library is loaded.
You may want to change the "Output profile" of your headphone to "High Fidelity Playback (AD2DP Sink)" to enhance the sound quality (see screenshot `sound-settings.png`).

This might already be sufficient.

Further tweaking is still possible:
Copy/Add the configuration-file `audio.conf` to the directory `/etc/bluetooth/.`.

Change your local configuration-file `/etc/bluetooth/main.conf` so that it contains:
```
ControllerMode = bredr
AutoEnable = true
```

## This solution comprises information gathered from:
https://erikdubois.be/installing-bose-quietcomfort-35-linux-mint-18/

Regarding the "a2dp-source profile connect failed for BLUETOOTH:DEVICE:ID: Protocol not available" error:
https://donjajo.com/bluetooth-fix-a2dp-source-profile-connect-failed-xx-protocol-not-available-linux/
