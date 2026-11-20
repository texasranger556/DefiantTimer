I have several Defiant light switch timers installed at my house.  The vendor has abandoned support for the Android app, so this is a backup of the .apk, and a vibe coded html replacement for the app.  Use at your own risk!


## Use the web app

Open **https://texasranger556.github.io/DefiantTimer/** in Chrome on your phone, then tap the menu (⋮) and **Install app** (or **Add to Home screen**). After the first visit it works offline.

1. Tap **Set location** and enter your latitude and longitude. The timer needs them for Dusk to Dawn.
2. Plug the phone into the timer with a 3.5 mm cable. Phones without a headphone jack need a USB-C to 3.5 mm adapter that has a built-in DAC.
3. Turn media volume all the way up, turn off sound effects (Dolby, equalizer), and send a command.

## How it works

The original app programs the timer with audio: a 7600 Hz square wave in 3 ms slots, Manchester encoded and sent three times. Each command carries the date, time, time zone, daylight-saving flag and location, plus a checksum. The encoder in `index.html` is a port of the app's `ToneFormatter` and `Toner` classes and matches the app's own test vectors.

## Files

- `index.html`: the web app
- `manifest.webmanifest`, `sw.js`, `icons/`: what makes it installable and work offline. Bump `VERSION` in `sw.js` whenever you change a file.
- `DefiantTimerRemote-offline.html`: single-file copy that runs without a server
- `DefiantTimer-1.1.5.apk`: backup of the original Android app (`com.smartec.appTimer`)
