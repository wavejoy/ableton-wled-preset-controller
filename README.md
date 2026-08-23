# ableton-wled-preset-controller

WLED Preset Controller for Ableton Live

A Max for Live device for triggering WLED presets directly from MIDI notes in Ableton Live.

Built for live production environments where lighting cues need to follow an Ableton session without relying on a separate lighting timeline or manual preset changes.

MIDI notes C1 through G8 map directly to WLED presets 1 through 92.

Features

* Trigger WLED presets directly from MIDI notes
* C1–G8 maps sequentially to presets 1–92
* Configurable WLED controller IP address
* Controller IP is saved with the Ableton Live Set
* Note-off messages are ignored
* Displays the most recently triggered note and preset
* Manual preset test control
* Uses WLED’s built-in HTTP control
* No additional WLED plugins or middleware required

MIDI Mapping

The mapping is sequential:

MIDI Note	WLED Preset
C1	1
C#1	2
D1	3
…	…
C2	13
C3	25
C4	37
C5	49
C6	61
C7	73
C8	85
G8	92

Every semitone advances to the next WLED preset.

Setup

1. Install the .amxd file in your Ableton Live User Library.
2. Add the device to a MIDI track.
3. Enter the IP address of your WLED controller.
4. Create or assign WLED presets 1–92 as needed.
5. Send MIDI notes from C1 through G8 to the device.

A MIDI note-on message recalls the corresponding WLED preset.

Network Recommendations

The device communicates with WLED over the network using HTTP.

It has been stable in my live-production use with ESP32-based WLED controllers.

For live shows, wired Ethernet/LAN is strongly recommended whenever possible.

Wi-Fi can work, but wireless reliability, congestion, roaming, and interference introduce variables that are generally best avoided for show-critical lighting control.

How It Works

The device converts incoming MIDI notes into WLED preset numbers and sends the corresponding command to the configured controller.

For example:

C1 → Preset 1
C#1 → Preset 2
D1 → Preset 3
...
G8 → Preset 92

Preset recalls are sent using WLED’s HTTP API.

Requirements

* Ableton Live with Max for Live
* WLED-compatible controller
* Network connection between the Ableton computer and WLED controller
* WLED presets configured on the target device

Live Production Notes

This device was built specifically for predictable preset recall during live playback.

For show use:

* Use a wired connection to the WLED controller when possible.
* Assign the controller a consistent IP address.
* Build and test all WLED presets before the show.
* Keep the Ableton computer and WLED controller on the same reliable production network.
* Test the complete cue path before doors.

Version

v1.1

Initial public release.

Issues & Contributions

If you encounter a problem, have an idea for an improvement, or want to contribute, feel free to open an issue or submit a pull request.

Disclaimer

This is an unofficial community project and is not affiliated with or endorsed by WLED or Ableton.
