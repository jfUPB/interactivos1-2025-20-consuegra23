# Unidad 2


## 🛠 Fase: Apply

### Actividad 4

### Actividad 5
``` py
from microbit import *
import utime
import speech

STATE_INIT = 0
STATE_ARMED = 1
STATE_KABOOM = 2

current_state = STATE_INIT
start_time = 20000

while True:
    if current_state == STATE_INIT:

        if button_a.was_pressed():
            start_time+= 1000
            if start_time > 60000:
                start_time = 60000
            print(start_time)
        if button_b.was_pressed():
            start_time-= 1000
            if start_time < 10000:
                start_time = 10000
            print(start_time)
        if accelerometer.was_gesture('shake'):
            current_state = STATE_ARMED
            print(start_time)
    if current_state == STATE_ARMED:
        divide_time = start_time // 5 
        start_tick = utime.ticks_ms()

        for i in range(5):
            while utime.ticks_diff(utime.ticks_ms(), start_tick) < divide_time * (i + 1):
                pass
            for col in range(5):
                display.set_pixel(col, i, 9)

        current_state = STATE_KABOOM
    if current_state == STATE_KABOOM:
        display.show(Image.SKULL)
        speech.say('BOOM')
        if button_a.was_pressed() or button_b.was_pressed():
            current_state = STATE_INIT
            display.clear()
```

