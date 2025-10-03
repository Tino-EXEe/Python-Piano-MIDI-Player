# Python-Piano-MIDI-Player
A Python program that plays any piano MIDI file using loopMIDI and VirtualMIDISynth.  It prints the notes in the terminal as they play, making it both fun and educational.  Supports all standard piano MIDI songs.


## Features
- Play any standard piano MIDI file
- Prints note names in the terminal while playing
- Works with Windows using loopMIDI + VirtualMIDISynth
- Easy to use and extend for other MIDI instruments

## Requirements
- Python 3.10+
- Libraries: `pygame`, `mido`, `python-rtmidi`
- [loopMIDI](https://www.tobias-erichsen.de/software/loopmidi.html) (virtual MIDI port)
- [VirtualMIDISynth](https://coolsoft.altervista.org/en/virtualmidisynth) (sound output)
- A piano SoundFont (e.g., [GeneralUser GS](https://schristiancollins.com/generaluser.php))

## How to Use
1. Install dependencies:
bash
pip install pygame mido python-rtmidi
2.Start loopMIDI and create a virtual port (e.g., Piano_MIDI).

3.Open VirtualMIDISynth and ensure the port is detected and a SoundFont is loaded.

4.Place your .mid file in the project folder.

5.Run this code to find  VirtualMIDISynth #1 Output :

import pygame.midi

pygame.midi.init()
print("Available MIDI devices:")
for i in range(pygame.midi.get_count()):
    interf, name, is_input, is_output, opened = pygame.midi.get_device_info(i)
    direction = "Input" if is_input else "Output"
    print(i, name.decode(), direction)
pygame.midi.quit()


