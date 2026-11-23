# iRacing Replay Markers Overlay

**Bookmark moments while you race in iRacing, then jump straight to them in the replay.**

iRacing Replay Markers Overlay is a tiny, always-on-top overlay for [iRacing](https://www.iracing.com/). You map a keyboard key or a steering wheel / button box button to **Mark**. Each time you press it during a session, the overlay saves the session time. When you open the replay later, use **Prev** and **Next** to step through every marker. You go straight to your incidents, contacts, overtakes, mistakes, or anything else you flagged, without scrubbing through the whole race.

> Keywords: iRacing replay markers, iRacing replay bookmarks, iRacing incident finder, iRacing overlay, sim racing replay tool, mark incidents in iRacing, iRacing replay jump to time, button box replay marker, wheel button bookmark.

---

## Why use it?

Finding one moment in a 45-minute iRacing replay is painful. Was the contact in lap 7 or lap 12? Where did you lose the tow? When did someone dive-bomb you into Turn 1?

With this overlay you **press one button while driving**, keep your hands on the wheel, and review everything after the race:

- 🚩 **Find your incidents fast.** Mark the moment you get an incident (or think you will) and jump right back to it.
- 📝 **Log things to review later:** a missed braking point, a good pass, a protest-worthy move, a setup issue.
- 🎥 **Clip highlights** for YouTube, Twitch, or Discord without hunting through the timeline.
- 🧑‍⚖️ **Gather evidence for protests** by going directly to the lap and moment.
- 📈 **Improve as a driver** by reviewing only the moments that mattered.

## Features

- **Mark / Prev / Next marker bar**: small, always on top, and out of the way.
- **Bind to any key or wheel button**: keyboard, steering wheel, button box, or other DirectInput / game controller buttons.
- **Saves the session time** for every marker you press during practice, qualifying, or the race.
- **Replay navigation**: step backward and forward through your saved markers while watching the replay.
- **Keeps your replay speed** when jumping between markers.
- **One-click setup and self-updates** from inside the overlay.
- **Styled like iRacing's own panels**, so it fits in on screen.
- **Lightweight**: a single small Python script that runs alongside iRacing.

## How it works

1. **Start the overlay** alongside iRacing (see [Installation](#installation)).
2. **Bind the Mark button** to a key or a button on your wheel or button box.
3. **Drive.** Press Mark whenever something happens that you want to look at later.
4. **Open the replay** after your session.
5. **Press Next / Prev** to jump the iRacing replay to each saved marker.

## Installation

**Requirements**

- Windows (the same PC you run iRacing on)
- [Python 3](https://www.python.org/downloads/windows/). The launcher opens the download page if Python is missing.
- iRacing in **Windowed** or **Borderless / fullscreen windowed** mode. In exclusive fullscreen, nothing can draw on top of iRacing.

**Setup (once)**

1. Download **`iracing-replay-markers-overlay.zip`** from the [latest release](https://github.com/slaythetrack/iracing-replay-markers-overlay/releases/latest).
2. Unzip it somewhere you'll keep it, for example `Documents`.
3. Double-click **`iRacing Replay Markers.bat`**.
   - **No Python yet?** The Python download page opens. Install Python 3 with **"Add python.exe to PATH"** ticked, then double-click the `.bat` again.
4. On first start, Settings opens and lists any missing packages. Click **Install missing**. The overlay restarts by itself when it's done. Until then, the bar shows **SETUP NEEDED** and the gear icon has an amber dot.

The packages are installed with pip:
- [`pyirsdk`](https://pypi.org/project/pyirsdk/) (required): talks to iRacing.
- [`keyboard`](https://pypi.org/project/keyboard/): keyboard hotkeys.
- [`pygame-ce`](https://pypi.org/project/pygame-ce/): steering wheel and button box buttons.

**Updating**

The overlay checks for a new version each time it starts. When there's one, the gear icon gets a yellow dot. Open Settings and click **Update now**. Your settings and markers are kept.

## Using it

- **Mark** saves the current moment, while you drive or while you watch a replay.
- **Prev / Next** jump between saved markers. iRacing only accepts replay jumps when you're **out of the car** (in the replay view).
- Each button lights up for a second: **green** means done, **amber** means nothing to do (no marker that way, or already marked), and **red** means it couldn't (iRacing isn't running, or you're still in the car).
- The ring on the left fills green while the overlay is connected to iRacing.
- **Move the bar:** drag any empty spot. **Resize it:** drag the grip in the bottom-right corner, or use Settings > Bar size.

### Key and wheel binds

Open Settings with the gear icon, or right-click > Settings. Click a bind box, then press a key combo (for example `Ctrl+Alt+M`) or the wheel or button box button you want. Esc cancels. The X clears a bind.

Default keyboard binds:

| Action | Default key |
|--------|-------------|
| Mark   | `Ctrl+Alt+M` |
| Prev   | `Ctrl+Alt+←` |
| Next   | `Ctrl+Alt+→` |

Settings also has opacity, bar size, and **how many seconds back a Mark lands**. That's useful if you tend to press Mark a moment after something happens.

### Where things are saved

- Settings are saved in `config.json`, next to `overlay.py`.
- Markers are saved per session in `%LOCALAPPDATA%\iracing-replay-markers-overlay`. Right-click the bar > **Open markers folder** to find them.

### Troubleshooting

- **Hotkeys don't work while iRacing is focused:** iRacing is probably running as administrator. Run the overlay as administrator too.
- **The overlay is hidden behind iRacing:** switch iRacing to Windowed or Borderless mode.
- **Prev / Next flash red:** get out of the car and into the replay view first.

## FAQ

**Does this work with my steering wheel or button box?**
Yes. That's the main use case. You can bind Mark (and Prev / Next) to a wheel or button box button, so you never take your hands off the wheel.

**Can I use it to find incidents in iRacing replays?**
Yes. Press Mark when an incident happens, then use Next / Prev in the replay to go straight back to it.

**Does it work in practice, qualifying, and races?**
Markers are saved against the session time, so you can mark moments in any iRacing session you can replay.

**Why do Prev / Next not work while I'm driving?**
iRacing only allows replay jumps when you're out of the car. Mark works while you're driving. Use Prev / Next from the replay view.

**Does it work in exclusive fullscreen?**
No. Windows can't draw an overlay on top of exclusive fullscreen. Run iRacing in Windowed or Borderless mode.

**Is it an iRacing official tool?**
No. This is an independent, community-made tool and is not affiliated with or endorsed by iRacing.com Motorsport Simulations.

## Contributing

Issues and pull requests are welcome. If you have an idea that would make reviewing iRacing replays easier, open an issue.

## License

See [LICENSE](LICENSE) if present.

---

_iRacing is a trademark of iRacing.com Motorsport Simulations, LLC. This project is not affiliated with iRacing._
