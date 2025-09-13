```python
#!/usr/bin/env python3
import time
import sys
import os
import random

SENSITIVITY = 0.2
FOV_RADIUS = 100
AIM_DURATION = 0.05

if os.system("command -v cliclick >/dev/null 2>&1") != 0:
    print("Error: cliclick not found. Install with: brew install cliclick")
    print("Get Homebrew from https://brew.sh")
    sys.exit(1)

def aim_at_target():
    dx = random.randint(-FOV_RADIUS, FOV_RADIUS) * SENSITIVITY
    dy = random.randint(-FOV_RADIUS, FOV_RADIUS) * SENSITIVITY
    os.system("cliclick m:+" + str(int(dx)) + ",+" + str(int(dy)))

print("Macsploit Aimbot ready. Type 't' and press Enter to toggle.")
print("Run Fortnite in GeForce NOW with PS5 controller connected.")
active = False
last_toggle = time.time()
while True:
    try:
        user_input = input()
        if user_input.lower() == "t" and time.time() - last_toggle > 0.5:
            active = not active
            print("[Macsploit] Aimbot " + ("ON" if active else "OFF"))
            last_toggle = time.time()
    except KeyboardInterrupt:
        print("Exiting Macsploit Aimbot.")
        break
    except:
        pass

    if active:
        aim_at_target()
    time.sleep(AIM_DURATION)
```
