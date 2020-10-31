# Thư viện mở rộng cho bộ kit xe điều khiển car:bit

```python
from carbit import *
import time

led_car = RGBcar()

new_car = Car()

bluetooth = Bluetooth_car()

ultrasonic_car = Ultrasonic_car()

if True:
  led_car.all_led("#33ccff")
  new_car.led_left(True)
  new_car.led_right(True)

while True:
  if bluetooth.check_bluetooth():
    if (bluetooth.msg_ble()) == 'F':
      new_car.forward(50)
    if (bluetooth.msg_ble()) == 'L':
      new_car.forward(30)
    if (bluetooth.msg_ble()) == 'R':
      new_car.forward(30)
    if (bluetooth.msg_ble()) == 'B':
      new_car.forward(50)
    if (bluetooth.msg_ble()) == 'stop':
      new_car.stop()

  print(ultrasonic_car.distance_cm())
  time.sleep_ms(100)
```
