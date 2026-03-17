# ASUS-TUF-Keyboard-Music-Sync

# 🎵 ASUS TUF Keyboard Music Sync

Syncs your ASUS TUF laptop's keyboard RGB lighting to audio in real time.

## Requirements

```bash
pip install numpy sounddevice openrgb-python
```

[OpenRGB](https://openrgb.org) must be installed and running with the SDK server enabled.
> Settings → SDK Server → Start Server

## Usage

```bash
python asus_music_sync.py --mode openrgb --device DEVICE_ID
```

To find your device ID, just run the script once — it will print a list of available audio inputs on startup. Use **Stereo Mix** to react to music playing on your PC, or your **Microphone** to react to room audio.

## Options

| Flag | Default | Description |
|---|---|---|
| `--mode` | `terminal` | `openrgb`, `wmi`, or `terminal` (preview) |
| `--device` | auto | Audio input device index |
| `--sensitivity` | `1.0` | Increase for quiet environments |
| `--smoothing` | `0.65` | `0` = snappy, `1` = slow/dreamy |

## Color Mapping

The keyboard cycles through the full spectrum based on volume:

`Deep Blue` → `Cyan` → `Lime` → `Yellow` → `Orange` → `Red` → `White flash (beat)`

When no audio is detected, the keyboard slowly cycles through a rainbow breathing animation.

## Notes

- On Windows, enable **Stereo Mix** by right-clicking the speaker icon → Sounds → Recording tab → right-click → Show Disabled Devices → Enable Stereo Mix
- Run OpenRGB as Administrator if your keyboard isn't detected
