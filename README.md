# Wake Words

Custom on-device [microWakeWord](https://github.com/kahrendt/microWakeWord) models
for our ESPHome voice satellites, trained with the reusable pipeline in
Home_Assistant_Setup/Wake_Word_Training. Referenced from firmware via
`github://CoreInnovation/wake-words/<word>.json@main`.

- **stop** - instant on-device interrupt word (say "stop" while the satellite is
  talking and it goes silent immediately, no round trip to Home Assistant).
