# Wake Words

Custom on-device [microWakeWord](https://github.com/kahrendt/microWakeWord) models
for our ESPHome voice satellites, trained with the reusable pipeline in
Home_Assistant_Setup/Wake_Word_Training. Referenced from firmware via
`github://CoreInnovation/wake-words/<word>.json@main`.

Wake words:

- **hey_nina** - THE wake word (94% recall / 0.19 faph @ 0.55). Variants
  ok_nina / hello_nina / hi_nina exist but are not loaded on-device.

Interrupt words (armed only from end-of-command to end-of-reply; they silence
playback via the hardware amp mute and go back to sleep):

- **nina_stop** / **nina_hush** - the single-syllable interrupts, Nina-prefixed
  (v17 rule, 2026-07-11): a bare "stop"/"hush" was too easy for the
  satellite's OWN reply audio to false-fire (speaker sits inches from the
  mic), so single-syllable stops require her name. 3000 samples;
  nina_stop 98.7% recall / ~1.7 faph @ 0.70, nina_hush ~96% recall /
  ~0-0.2 faph @ 0.70.
- **never_mind** / **shut_up** - multi-word interrupts, still bare
  (96% recall @ 0.6 for never_mind). be_quiet / cancel are trained and
  published but not currently loaded (tensor arena budget).
- **stop** - RETIRED from the satellite in v17 (replaced by nina_stop);
  kept here for other devices or a future retrain with her own TTS voice
  as negative data.
