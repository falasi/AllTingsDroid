# Trickery Bypasses

# ADB Common Commands

## 💤 Keep Screen Awake (Bypass Screen Timeout)

If your Android device has ADB access, you can bypass screen timeout or lock policies by simulating user input:

### Manual Commands
```bash
adb shell input keyevent 224                 # Wake up the screen
adb shell input touchscreen tap 500 500      # Tap the center of the screen
```

### Bash Script (Auto-Tap Every 10 Seconds)

This script keeps the screen awake by simulating touch input in an infinite loop.
```
#!/bin/bash

# Make sure device is connected
echo "Keeping Android screen awake with ADB every 10 seconds..."
echo "Press [Ctrl+C] to stop."

while true; do
  adb shell input keyevent 224         # Wake up screen
  adb shell input touchscreen tap 500 500  # Tap middle of screen
  sleep 10
done

```
